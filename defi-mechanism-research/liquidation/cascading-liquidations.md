# Cascading Liquidations

## Overview

Cascading liquidations occur when multiple positions are liquidated simultaneously, creating a feedback loop that amplifies market downturns. These events represent one of the most significant systemic risks in DeFi, as they can trigger protocol insolvency, market crashes, and contagion across interconnected protocols.

## Trigger Dynamics

### Initial Trigger
- **Black swan event**: Sudden market crash or news-driven panic
- **Large whale position**: Single large position gets liquidated
- **Oracle failure**: Incorrect price feeds trigger mass liquidations
- **Protocol exploit**: Hack creates panic selling

### Cascade Mechanism
1. Price drops → Health factors fall below threshold
2. Liquidators begin selling collateral
3. Selling pressure drives prices lower
4. More positions become eligible for liquidation
5. Cycle repeats, accelerating the downward spiral

### Amplification Factors
- **High leverage**: More positions near liquidation threshold
- **Correlated collateral**: Multiple protocols holding same assets
- **Low liquidity**: Less market depth to absorb liquidations
- **Panic psychology**: Users withdraw funds simultaneously

## Feedback Loops

### Price-Liquidation Loop
- Liquidation → Price drop → More liquidations → Further price drops
- Self-reinforcing cycle that accelerates market decline
- Can continue until market finds natural bottom or intervention occurs

### Cross-Protocol Contagion
- One protocol's liquidations affect asset prices
- Other protocols holding same assets see health factors decline
- Cascades spread across multiple protocols

### Liquidity Feedback
- Liquidations require buyers
- If buyers are scarce, prices drop further
- Low liquidity → Higher slippage → More liquidations

## Market Impact

### Price Volatility
- Rapid, extreme price swings
- Can exceed normal market volatility significantly
- Recovery can be slow due to loss of confidence

### Liquidity Effects
- Market makers may withdraw during cascade
- Liquidity pools can become imbalanced
- Trading costs spike during crisis

### Psychological Impact
- User confidence erodes
- New users avoid DeFi
- Protocol reputational damage

## Systemic Contagion

### Inter-protocol Dependencies
- Shared collateral assets across protocols
- Lending/borrowing relationships between protocols
- Oracle dependencies create correlated risks

### Capital Flight
- Users withdraw funds from affected protocols
- TVL drops dramatically
- Reduced protocol revenue and sustainability

### Regulatory Response
- Increased scrutiny after major cascades
- Potential regulatory intervention
- Impact on broader DeFi ecosystem

## Mitigation Strategies

### Protocol Level
- **Conservative parameters**: Lower LTV ratios, higher thresholds
- **Gradual liquidation**: Limit per-block liquidation volume
- **Circuit breakers**: Pause during extreme market conditions
- **Insurance funds**: Cover losses from cascading events

### Market Level
- **Deep liquidity**: Ensure sufficient market depth
- **Diversified collateral**: Reduce correlation risks
- **Stress testing**: Regular simulation of cascade scenarios
- **Emergency protocols**: Pre-defined response procedures

### User Level
- **Maintain healthy positions**: Keep health factor well above 1
- **Monitor market conditions**: Exit during high volatility periods
- **Diversify across protocols**: Don't concentrate all assets
- **Set alerts**: Automatic notifications for health factor changes

## Open Questions

- How can protocols better predict and prevent cascade events?
- What is the role of centralized intervention during DeFi cascades?
- Can cross-protocol coordination reduce systemic cascade risk?
