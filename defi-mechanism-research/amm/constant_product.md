# Constant Product AMM

## Overview

Constant Product Market Makers (CPMMs) are the foundational mechanism behind early automated market makers like Uniswap V2. The core principle is maintaining a constant product between two asset reserves:

```
x * y = k
```

Where:
- `x` = reserve of token A
- `y` = reserve of token B
- `k` = constant product (invariant)

This ensures that as one asset is bought (increasing its reserve), the other asset's price rises proportionally, providing continuous liquidity.

## Core Formula

The relationship between reserves is maintained by:

```
x * y = k
```

When a trade occurs:
- `Δx` = amount of token A added to pool
- `Δy` = amount of token B removed from pool (or vice versa)

The new reserves must still satisfy:
```
(x + Δx) * (y - Δy) = k
```

Solving for price:
```
dy/dx = -y/x
```

This represents the instantaneous price of token A in terms of token B.

## Mechanism Design

### Liquidity Provision
- Liquidity providers (LPs) deposit equal value amounts of both tokens
- Receive LP tokens representing their share of total pool
- Earn fees proportional to their pool share

### Trading Mechanics
- Users swap by adding one token and receiving the other
- Pool adjusts prices according to the curve
- Fees are added to the pool, increasing `k` over time

### Price Impact
- Larger trades cause greater price slippage
- Smaller trades near the center of the curve have lower impact
- Formula naturally prevents complete depletion of reserves

## Incentives

### For Liquidity Providers
- **Trading fees**: Earn percentage of all swaps in proportion to pool share
- **Impermanent loss compensation**: Fees should ideally exceed IL over time

### For Traders
- **Continuous liquidity**: Always able to trade within the bounds of the curve
- **Price discovery**: Transparent pricing based on reserve ratios

## Risks

### Impermanent Loss
- Occurs when external market prices diverge from the pool's internal price
- LPs lose value compared to holding assets outside the pool
- Severity increases with volatility

### Front-running and MEV
- Arbitrageurs can exploit price differences between AMMs and centralized exchanges
- Sandwich attacks target large trades for additional profits

### Low Capital Efficiency
- Capital locked in wide price ranges where little trading occurs
- Reserves depleted during extreme market movements

## Notable Protocol Examples

- **Uniswap V2**: Original implementation with 0.3% fee
- **SushiSwap**: Fork with staking incentives
- **PancakeSwap**: BSC implementation with yield farming

## Open Questions

- How can CPMMs be optimized for capital efficiency?
- What are the limits of pure constant product models versus hybrid approaches?
- How do external oracle integrations affect stability?
