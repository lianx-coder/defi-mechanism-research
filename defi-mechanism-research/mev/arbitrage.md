# Arbitrage

## Overview

MEV (Maximal Extractable Value) arbitrage in DeFi refers to the practice of exploiting price discrepancies across decentralized exchanges and lending protocols. Unlike traditional arbitrage, DeFi arbitrageurs operate within block builders' control, allowing them to order transactions for maximum profit extraction.

## Cross-DEX Arbitrage

### Price Discrepancies
- Different AMMs may have different prices for same asset pair
- Liquidity imbalances create temporary price differences
- Arbitrageurs exploit these differences for risk-free profit

### Common Pairs
- ETH/USDC across Uniswap, SushiSwap, Curve
- Stablecoin pairs (USDC/USDT/DAI)
- Cross-chain wrapped assets

### Profit Mechanism
```
Buy on DEX A (lower price) -> Sell on DEX B (higher price)
```

## Price Discovery Role

### Market Efficiency
- Arbitrageurs help maintain price alignment across venues
- Reduce price discrepancies quickly
- Contribute to overall market efficiency

### Information Asymmetry
- MEV extractors have advantage through faster execution
- Block ordering provides execution certainty
- Profit comes from timing and positioning advantages

## Competition Dynamics

### Competition Intensity
- High competition reduces individual profits
- Race conditions: multiple arbitrageurs target same opportunity
- Gas auctions: Bidders compete for transaction ordering priority

### Winner-Takes-All
- Only one transaction can capture each opportunity
- Highest gas bidder typically wins
- Remaining bidders lose gas costs

### MEV-Boost and Flashbots
- Reduces competition through private channels
- Bundle ordering eliminates gas wars
- More efficient price discovery but less transparent

## Risks and Frictions

### Execution Risk
- Transaction may fail if market moves during execution
- Slippage can eliminate expected profits
- Gas costs may exceed profit margin

### MEV-Related Risks
- Block reorganizations can undo transactions
- Competition from sophisticated actors
- Regulatory scrutiny of MEV practices

### Market Risks
- Sudden price movements can turn profitable trades into losses
- Liquidity constraints limit trade sizes
- Oracle manipulation can create false arbitrage signals

## Notable Examples

### Flash Loan Arbitrage
- Use flash loans to execute large arbitrage trades
- No capital requirement, but must repay in same transaction
- Popular during high-volatility periods

### Stablecoin Arbitrage
- Exploit price differences between stablecoins
- Low risk due to pegged values
- Requires large volumes for meaningful profits

### Cross-Chain Arbitrage
- Exploit price differences across different blockchains
- More complex due to bridge mechanisms
- Higher risk due to cross-chain settlement times

## Open Questions

- How does MEV arbitrage affect overall DeFi market efficiency?
- Can decentralized block building reduce MEV extraction?
- What is the social cost of competitive MEV extraction?
