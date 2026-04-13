# Liquidation Risk

## Overview

Liquidation risk is a fundamental concern in over-collateralized DeFi lending. It represents the probability that a borrower's collateral value falls below the required threshold, triggering forced sale of collateral at potentially unfavorable prices. Understanding and managing liquidation risk is critical for both borrowers seeking leverage and protocols maintaining solvency.

## Collateral Health Metrics

### Health Factor
- Composite metric of position safety
- Formula: `(collateral_value * liquidation_threshold) / borrowed_value`
- Health > 1: Position healthy
- Health ≤ 1: Position eligible for liquidation

### Liquidation Threshold
- Percentage of collateral value usable for borrowing
- Typically 50-85% depending on asset volatility
- Lower threshold = higher risk tolerance but lower capital efficiency

### Collateral Value Calculation
- Real-time valuation using oracle prices
- Haircut applied to collateral value (e.g., 15-30% for volatile assets)
- Stale oracle data can create unexpected liquidations

## Volatility and Slippage

### Asset Volatility Impact
- High volatility assets have higher liquidation probability
- Sharp price moves can trigger cascade liquidations
- Correlation between collateral and borrowed assets matters

### Liquidation Slippage
- Liquidators sell collateral on open market
- Large liquidations cause market impact
- Slippage加剧了借款人的损失

### Price Impact Cascades
- Multiple positions liquidating simultaneously
- Creates feedback loop: liquidation → price drop → more liquidations
- Particularly severe in low-liquidity markets

## Oracle Dependency

### Oracle Failure Modes
- **Stale prices**: Delayed updates allow arbitrage
- **Flash crashes**: Single oracle spike triggers unnecessary liquidations
- **Manipulation**: Targeted oracle attacks during low liquidity

### Oracle Solutions
- **Time-weighted average prices (TWAP)**: Smooths short-term volatility
- **Decentralized oracle networks**: Multiple data sources
- **Staleness thresholds**: Reject prices older than X seconds

### Mitigation Strategies
- Use multiple independent oracles
- Implement circuit breakers
- Add price deviation checks

## Systemic Risk

### Contagion Effects
- Large protocol liquidations affect overall market
- One protocol's cascade can trigger others
- Correlated collateral across protocols amplifies risk

### Market Depth Dependencies
- Liquidations require buyers
- Low market depth = higher slippage
- During crises, buyers may be scarce

### Governance Risk
- Parameter changes can increase liquidation risk
- Emergency controls may be too slow
- Socialized losses vs. covered by protocol reserves

## Mitigation Strategies

### Borrower Side
- **Over-collateralization**: Maintain health factor well above 1
- **Diversified collateral**: Mix stable and volatile assets
- **Active monitoring**: Set alerts for health factor changes
- **Yield hedging**: Reduce exposure to collateral depreciation

### Protocol Side
- **Conservative thresholds**: Lower LTV ratios for volatile assets
- **Gradual liquidation**: Limit per-block liquidation volume
- **Auction mechanisms**: Competitive liquidation vs. fixed bonus
- **Emergency shutdown**: Pause during extreme market conditions

## Open Questions

- How can protocols better predict and prevent cascade liquidations? ([See cascading liquidations](../liquidation/cascading-liquidations.md))
- What is the optimal balance between capital efficiency and liquidation safety? ([See concentrated liquidity](../amm/concentrated_liquidity.md))
- Can decentralized liquidation mechanisms reduce market impact during crises? ([See liquidation mechanism](../liquidation/liquidation-mechanism.md))
