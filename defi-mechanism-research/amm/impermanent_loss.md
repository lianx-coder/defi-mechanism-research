# Impermanent Loss

## Overview

Impermanent Loss (IL) is the difference between the value of holding assets in an AMM liquidity pool versus holding them outside the pool as prices fluctuate. The term "impermanent" reflects that losses only become permanent upon withdrawal from the pool.

IL affects all AMMs but manifests differently in constant product vs concentrated liquidity models.

## Why It Happens

### Constant Product AMMs (V2-style)
- Pool rebalances automatically as prices move
- LPs end up holding more of the declining asset and less of the rising asset
- At withdrawal, LPs face a portfolio composition that may be unfavorable

### Concentrated Liquidity AMMs (V3-style)
- IL amplified when positions exit their active price range
- Positions become concentrated in one asset as price moves away
- LPs may face directional exposure they didn't intend

### Mathematical Foundation
- In constant product models: IL = 2√(HODL_value * AMM_value) - (HODL_value + AMM_value)
- Worst case occurs with 100x+ price movement: ~35% loss
- Concentrated positions can experience much higher IL depending on range

## Mathematical Intuition

### Constant Product IL Formula
For a price change ratio `r` (new_price / old_price):

```
IL = (2 * sqrt(r)) / (1 + r) - 1
```

### Concentrated Liquidity IL
- Depends on position range width
- Non-linear relationship with price movement
- Can exceed 50%+ in extreme cases

### Visual Representation
- Symmetric loss curve in V2 (U-shaped)
- Asymmetric loss in V3 depending on range placement

## LP Tradeoffs

### Fees vs IL Balance
- Higher trading volume increases fee income
- High volatility increases IL magnitude
- Optimal LP strategy balances both factors

### Range Selection Impact
- Tight ranges: Higher fees per liquidity but more frequent range exits
- Wide ranges: Lower IL risk but lower fee efficiency
- Must consider asset correlation and volatility

## Risk Mitigation

### Position Diversification
- Spread liquidity across multiple ranges
- Combine different position widths
- Mix stable and volatile pair strategies

### Active Management
- Rebalance positions as prices move
- Close positions before major range exits
- Monitor IL metrics in real-time

### Protocol-Level Solutions
- Fee tier selection (0.05%, 0.3%, 1% in Uniswap V3)
- Concentration adjustments
- Dynamic fee mechanisms based on volatility

## Case Studies

### Stablecoin Pairs
- Low volatility reduces IL risk
- Tight ranges often optimal
- Fee income typically dominates IL

### Highly Correlated Assets
- ETH/WETH, BTC/wBTC pairs
- Minimal IL due to correlated movement
- Focus shifts to fee capture

### High Volatility Pairs
- Crypto-native tokens
- Significant IL risk
- Requires sophisticated range management

## Open Questions

- Can dynamic range adjustment algorithms eliminate IL? ([See concentrated liquidity](../amm/concentrated_liquidity.md))
- How do cross-protocol arbitrageurs affect IL distribution? ([See arbitrage](../mev/arbitrage.md))
- What role does IL play in overall DeFi ecosystem sustainability? ([See constant product](../amm/constant_product.md))
