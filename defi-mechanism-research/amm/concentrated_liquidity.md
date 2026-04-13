# Concentrated Liquidity

## Overview

Concentrated Liquidity represents a fundamental advancement in Automated Market Maker design, pioneered by Uniswap V3. Unlike constant product AMMs that spread liquidity across all price ranges, concentrated liquidity allows liquidity providers (LPs) to allocate capital within specific price ranges (ticks).

This innovation dramatically improves capital efficiency by allowing LPs to focus their deposits where trading is most likely to occur, rather than spreading capital thinly across infinite price ranges.

## How It Works

### Tick System
- Prices are discretized into "ticks" (e.g., every 0.01%)
- LPs can deposit liquidity between specific tick ranges
- Each tick represents a specific price ratio between two tokens

### Position Management
- LPs create "positions" with defined price ranges (lowerTick, upperTick)
- Liquidity is only active when the current price falls within the range
- Outside the range, positions hold only one token

### Virtual Reserves
- Uses virtual reserves to maintain the constant product invariant
- Real and virtual reserves work together to provide effective liquidity
- Allows for precise liquidity allocation without breaking AMM mechanics

## Capital Efficiency

### Improved Capital Utilization
- LPs can achieve 4000x+ higher capital efficiency compared to V2
- Liquidity concentrated where trading actually happens
- Reduced capital requirements for maintaining the same price impact

### Flexible Position Sizing
- LPs can size positions according to their conviction
- Multiple positions can cover different price ranges
- Positions can be managed independently

## LP Position Management

### Range Selection Strategy
- **Stable pairs**: Tight ranges around peg
- **Volatility pairs**: Wide ranges to avoid being out of range
- **Directional bets**: Asymmetric ranges for directional exposure

### Rebalancing Considerations
- Positions become concentrated in one token as price moves
- Manual rebalancing required to maintain exposure
- Impermanent loss dynamics differ significantly from V2

### Fee Accrual Mechanics
- Fees accrue only when price is within the position range
- Positions earn fees proportional to their active liquidity share
- Complex fee calculations due to dynamic range inclusion

## Risks

### Being Out of Range
- Positions earn zero fees when price moves outside range
- Capital inefficient if price remains far from range
- Requires active management to remain profitable

### Impermanent Loss Amplification
- Concentrated positions can experience amplified IL during range exits
- Risk increases with position width and volatility
- Directional exposure creates asymmetric risk profiles

### Complexity and Gas Costs
- More complex position management than V2
- Higher gas costs for creating and managing positions
- Requires sophisticated strategies for optimization

## Notable Protocol Examples

- **Uniswap V3**: Pioneer of concentrated liquidity
- **Balancer V2**: Supports concentrated liquidity pools
- **PancakeSwap V3**: BSC implementation of concentrated liquidity
- **SushiSwap K**: Concentrated liquidity fork

## Open Questions

- How can automated position management be improved?
- What are optimal strategies for range selection?
- How does concentrated liquidity affect market making competition?
