# Liquidation Mechanism

## Overview

Liquidation mechanisms are critical safety components in over-collateralized DeFi lending protocols. They protect lenders from bad debt by automatically selling borrower collateral when positions become under-collateralized. The design of liquidation systems directly impacts protocol stability, capital efficiency, and user experience.

## Trigger Conditions

### Health Factor Calculation
- Formula: `(collateral_value * liquidation_threshold) / borrowed_value`
- Trigger: Health Factor ≤ 1.0
- Different thresholds per asset (stablecoins vs volatile assets)

### Price Oracle Requirements
- Real-time price feeds essential for accurate health calculation
- Stale or manipulated prices can cause incorrect liquidations
- Multiple oracle sources improve reliability

### Partial vs Full Liquidation
- **Full liquidation**: Entire position liquidated (early models)
- **Partial liquidation**: Only enough to restore health factor (modern)
- **Gradual liquidation**: Limit per-block liquidation volume

## Keeper / Liquidator Role

### Keeper Operations
- Monitor health factors across protocols
- Submit liquidation transactions
- Execute profitable liquidations

### Liquidator Incentives
- **Liquidation bonus**: 5-15% of liquidated collateral
- **Priority access**: Immediate collateral access
- **Arbitrage opportunities**: Price differences in liquidation sales

### Competition Dynamics
- Gas auctions for liquidation rights
- MEV competition for most profitable opportunities
- Infrastructure advantages (speed, monitoring tools)

## Incentive Design

### Borrower Incentives
- Maintain health factor > 1.5 to avoid liquidation
- Monitor positions actively
- Add collateral or repay when needed

### Liquidator Incentives
- Maximize profit per liquidation
- Minimize gas costs
- Competitive advantage through speed and accuracy

### Protocol Incentives
- Maintain solvency
- Minimize bad debt
- Optimize capital efficiency

## Auction or Fixed Bonus Model

### Fixed Bonus Model (Traditional)
- Constant liquidation percentage (e.g., 10%)
- Simple to understand and implement
- May not be optimal during market stress

### Dutch Auction Model
- Starting with high bonus, decreasing over time
- Encourages faster liquidations
- Can achieve better price discovery

### Continuous Auction Model
- Multiple liquidators compete simultaneously
- Market-driven liquidation pricing
- More efficient price discovery

## Risks

### Liquidation Cascade
- Multiple positions liquidating simultaneously
- Market impact from large liquidations
- Feedback loop: liquidation → price drop → more liquidations

### Oracle Manipulation
- Flash loan attacks to trigger false liquidations
- Price manipulation during low liquidity
- Stale oracle data creating incorrect health calculations

### Keeper Centralization
- Few entities control most liquidation infrastructure
- Potential for collusion
- Systemic risk if key players fail

## Open Questions

- Can liquidation mechanisms be designed to be more resilient during market stress? ([See cascading liquidations](../liquidation/cascading-liquidations.md))
- How do different auction models perform in practice? ([See interest rate model](../lending/interest-rate-model.md))
- What is the optimal balance between liquidator incentives and protocol stability? ([See lending models](../lending/lending-models.md))
