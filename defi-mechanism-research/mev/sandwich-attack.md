# Sandwich Attack

## Overview

A sandwich attack is a form of Maximal Extractable Value (MEV) where an attacker exploits a victim's pending transaction by placing transactions before and after it in the same block. This allows the attacker to profit from the price impact of the victim's trade while minimizing their own risk.

## Attack Flow

### Step-by-Step Process
1. **Victim Transaction**: User submits a large swap transaction (e.g., buying ETH with USDC)
2. **Front-run**: Attacker buys ETH first, driving up price
3. **Victim Executes**: Victim buys ETH at inflated price due to front-run
4. **Back-run**: Attacker sells ETH at the higher price, capturing profit

### Block Construction
```
[Attacker Buy] -> [Victim Swap] -> [Attacker Sell]
```

### Gas Strategy
- Front-run: Higher gas price to ensure inclusion before victim
- Back-run: Standard gas price (profit comes from price difference)
- Total cost: Gas for two transactions

## Preconditions

### Transaction Visibility
- Attacker must see victim transaction in mempool
- Requires running a node or using mempool monitoring service
- Private mempools (like Flashbots) can prevent some attacks

### Sufficient Slippage Tolerance
- Victim must allow sufficient price slippage
- Typical DeFi swaps allow 0.5-5% slippage
- Attacker needs slippage window to profit

### Adequate Liquidity
- Pool must have enough depth for both transactions
- Very small pools may not allow profitable attacks
- Large pools enable larger attack sizes

## Victim Impact

### Direct Cost
- Victim pays higher price due to front-run
- Receives fewer assets than expected
- Loss proportional to trade size and slippage tolerance

### Indirect Effects
- Erodes trust in DeFi systems
- Discourages large trades
- May push users to private transaction relayers

### Economic Impact
- Extracts value from users without providing service
- Represents a transfer from users to attackers
- Can exceed protocol fees in high-volume periods

## Detection and Measurement

### On-Chain Indicators
- Identical sender for first and last transaction in triplet
- Same token pair in all three transactions
- Profit calculation: (back_run_sell - front_run_buy) - gas_costs

### Mempool Monitoring
- Track pending transactions for potential targets
- Analyze gas prices and transaction ordering
- Use specialized MEV monitoring tools

### Statistical Analysis
- Cluster analysis of transaction triplets
- Time-series analysis of attack frequency
- Correlation with network congestion

## Mitigations

### For Users
- **Reduce slippage tolerance**: Lower acceptable price impact
- **Use private mempools**: Flashbots Protect, BloXroute
- **Break large trades**: Split into smaller transactions
- **Time trades**: Avoid peak congestion periods

### For Protocols
- **MEV-resistant designs**: Batch auctions, TWAP oracles
- **Fair ordering**: Enforce first-come-first-serve
- **Return MEV to users**: Rebate excess profits
- **Limit transaction size**: Prevent large single swaps

### Infrastructure Level
- **Encrypted mempools**: Prevent transaction observation
- **Threshold encryption**: Decrypt only after block finalization
- **Commit-reveal schemes**: Hide transaction details initially

## Open Questions

- How does the rise of private transaction relayers affect public MEV?
- Can protocol-level MEV redistribution eliminate harmful attacks?
- What role does transaction privacy play in DeFi security?
