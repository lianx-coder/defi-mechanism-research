# Lending Models

## Overview

DeFi lending protocols enable permissionless borrowing using over-collateralized loans. These systems create liquidity pools where lenders deposit capital to earn interest, while borrowers post collateral to access funds. Unlike traditional finance, DeFi lending operates without credit checks, relying instead on collateralization ratios and liquidation mechanisms.

## Pool-Based Lending

### Architecture
- Lenders deposit assets into shared pools
- Borrowers tap into available liquidity
- Interest rates determined by utilization (borrowed/total)

### Interest Rate Curves
- **Stable phase**: Low utilization = low rates
- **Kink point**: Moderate utilization = moderate rates
- **High utilization**: Approaches maximum rate

### Collateral Frameworks
- **Collateral Factor**: Percentage of collateral value usable for borrowing
- **Liquidation Threshold**: Point at which positions become eligible for liquidation
- **Liquidation Bonus**: Incentive for liquidators (typically 5-10%)

## Peer-to-Peer Lending

### Direct Matching
- Borrowers matched directly with lenders
- Eliminates pool risk concentration
- Requires sufficient liquidity depth

### Isolated Markets
- Each borrower-lender pair operates independently
- Risk contained to individual relationships
- Limited scalability compared to pooled models

## Collateral Frameworks

### Single Collateral
- Borrow same asset deposited
- Simple risk management
- Limited flexibility

### Cross-Collateralization
- Deposit one asset, borrow another
- Increased capital efficiency
- Complex risk correlations

### Oracle Dependencies
- Real-time price feeds critical for safety
- Flash loan attacks can manipulate prices
- Multiple oracle sources improve resilience

## Incentives

### For Lenders
- **Supply APY**: Earn interest from borrowers
- **Protocol rewards**: Additional tokens for participation
- **Risk-adjusted returns**: Higher yields for riskier assets

### For Borrowers
- **Access to leverage**: Increase position sizes
- **No KYC**: Permissionless borrowing
- **Flexible repayment**: No fixed terms

### For Liquidators
- **Liquidation bonuses**: Profit from liquidating positions
- **Arbitrage opportunities**: Capture market inefficiencies
- **System stability**: Maintain protocol health

## Risks

### Smart Contract Risk
- Bugs in lending logic
- Upgrade vulnerabilities
- Integration failures

### Market Risk
- **Black swan events**: Extreme price movements
- **Oracle manipulation**: Artificial price changes
- **Correlation breakdowns**: Collateral and borrowed asset move together

### Credit Risk
- **Insufficient collateralization**: Liquidation delays
- **Liquidation cascade**: Multiple positions liquidated simultaneously
- **Bad debt**: Unable to recover full loan value

## Open Questions

- How can peer-to-peer matching scale effectively?
- What is the optimal balance between centralization and decentralization in lending pools?
- How do cross-chain lending protocols handle oracle and liquidation complexity?
