# Interest Rate Model

## Overview

Interest rate models in DeFi lending protocols determine the cost of borrowing and the return for lenders. These models are critical for protocol stability, capital efficiency, and market equilibrium. Unlike traditional finance with centralized rate setting, DeFi protocols use algorithmic, utilization-based rate mechanisms.

## Utilization-Based Curves

### Definition
- **Utilization (U)**: Percentage of supplied assets that are borrowed
- `U = borrowed / supplied`
- Rates increase as utilization rises

### Why Utilization-Based?
- Natural market equilibrium: High demand → higher rates → more supply
- Self-correcting mechanism: Extremely high rates encourage repayment
- Transparent and predictable: No centralized rate setting

### Basic Linear Model
```
rate = base_rate + slope * U
```

### Multi-Slope Models (Kink Model)
```
if U < kink_point:
    rate = base_rate + slope_low * U
else:
    rate = base_rate + slope_low * kink_point + slope_high * (U - kink_point)
```

## Borrow and Supply Rates

### Borrow Rate
- Cost for borrowers to take loans
- Directly tied to protocol utilization
- Paid by borrowers, distributed to lenders (minus protocol fees)

### Supply Rate
- Return for lenders supplying capital
- Always ≤ borrow rate (after fees)
- Formula: `supply_rate = borrow_rate * (1 - reserve_factor) * U`

### Rate Equilibrium
- When `U = 0%`: Rate = base rate (minimal return)
- When `U = 100%`: Rate = maximum (infinite in theory, capped in practice)
- Target utilization typically 80-90%

## Kink Models

### Purpose
- Creates rate acceleration at specific utilization thresholds
- Prevents dangerous over-borrowing scenarios
- Incentivizes supply when most needed

### Standard Implementation (Aave-style)
- **Optimal utilization**: ~80%
- **Base rate**: 0-3% depending on asset
- **Slope 1**: 4-10% (normal conditions)
- **Slope 2**: 100%+ (aggressive penalty)

### Parameter Tuning
- Based on historical utilization patterns
- Asset volatility considerations
- Target protocol risk profile

## Incentive Effects

### Supply Response
- Higher rates attract more lenders
- Supply elasticity depends on alternative yields
- Stablecoins typically highly elastic

### Borrow Response
- Higher rates discourage new borrowing
- Encourage early repayment
- Reduce utilization risk

### Market Dynamics
- Competitive rates attract TVL
- Rate arbitrage between protocols
- Cross-protocol yield optimization

## Risks

### Rate Miscalibration
- Too low: Protocol liquidity crunch
- Too high: Uncompetitive, borrowers leave
- Must balance borrower and lender interests

### Utilization Spikes
- Sudden price drops trigger mass borrowing
- Liquidation cascade increases borrowing demand
- Rate mechanisms may lag behind crisis

### Inter-protocol Dependencies
- Rates affected by overall market conditions
- Correlations between asset utilizations
- Contagion from other protocol failures

## Open Questions

- How do dynamic rate models perform during black swan events?
- Can AI/ML improve rate parameter optimization?
- What is the optimal rate mechanism for multi-collateral, cross-chain lending?
