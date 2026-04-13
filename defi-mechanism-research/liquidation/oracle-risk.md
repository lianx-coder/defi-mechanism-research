# Oracle Risk

## Overview

Oracle risk refers to the vulnerabilities and failure modes associated with price feeds in DeFi protocols. Since most DeFi lending, liquidation, and trading systems depend on accurate, timely price data, oracle manipulation or failure can lead to catastrophic losses, incorrect liquidations, or protocol insolvency.

## Pricing Dependencies

### Oracle Types
- **On-chain price feeds**: Chainlink, Band, Tellor
- **Off-chain price feeds**: API-based, centralized sources
- **Hybrid models**: Combine multiple sources
- **Custom oracles**: Protocol-specific implementations

### Asset Coverage
- Major assets: Typically have multiple oracle sources
- Long-tail assets: Limited oracle coverage
- Stablecoins: Often pegged, but can depeg during stress
- Cross-chain assets: Bridge and oracle complexity

### Update Frequency
- Real-time vs periodic updates
- Staleness thresholds
- Block-by-block updates for critical assets
- Gas cost considerations for frequent updates

## Manipulation Vectors

### Flash Loan Attacks
- Borrow large amounts to manipulate prices temporarily
- Trigger liquidations at favorable prices
- Repay loan, keep profit

### Spot Price Manipulation
- Target low-liquidity pools
- Large trades to move price temporarily
- Exploit protocols using spot prices instead of TWAP

### Oracle Feed Manipulation
- Compromise oracle operators
- Submit false price data
- Coordinate with other attacks

### Time-Based Attacks
- Exploit slow oracle updates
- Front-run price updates with large trades
- Manipulate during oracle downtime

## Latency and Liveness

### Latency Issues
- Price feeds lag behind market movements
- During high volatility, stale prices create risk
- Delayed updates can trigger incorrect liquidations

### Liveness Failures
- Oracle feed goes offline
- Network congestion prevents updates
- Protocol continues with stale data

### Mitigation for Latency/Liveness
- Circuit breakers when data is stale
- Fallback price sources
- Graceful degradation of protocol functions
- Emergency pause mechanisms

## Oracle Design Tradeoffs

### Decentralization vs Efficiency
- More decentralized = more robust but slower
- Centralized oracles = faster but single point of failure
- Hybrid approaches attempt to balance both

### Accuracy vs Cost
- High-frequency updates cost more gas
- Infrequent updates reduce accuracy
- Protocol must balance cost and precision

### Complexity vs Reliability
- Simple oracle systems are easier to audit
- Complex systems offer more features but harder to secure
- Integration complexity increases attack surface

## Mitigation Strategies

### Technical Solutions
- **Multiple oracle sources**: Consensus across different feeds
- **Time-weighted average prices (TWAP)**: Smooth short-term volatility
- **Staleness checks**: Reject prices older than threshold
- **Price deviation limits**: Flag abnormal changes

### Protocol Design
- **Conservative LTV ratios**: Account for oracle risk
- **Circuit breakers**: Pause during oracle issues
- **Emergency shutdown**: Protect users during oracle failures
- **Insurance funds**: Cover losses from oracle manipulation

### Operational Practices
- Monitor oracle health continuously
- Test failure scenarios regularly
- Maintain fallback price sources
- Document oracle dependencies clearly

## Open Questions

- How can protocols achieve true oracle resilience?
- What is the role of decentralized oracle networks vs traditional price feeds?
- Can protocols operate safely without oracle dependencies?
