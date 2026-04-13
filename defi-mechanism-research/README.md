# DeFi Mechanism Research

A research repository analyzing the core mechanisms that power decentralized finance.

This repo breaks down the economic and technical structures behind major DeFi primitives such as Automated Market Makers, lending markets, MEV extraction, and liquidation engines.

The goal is to document how these systems work under the hood and highlight potential risks, incentives, and design tradeoffs.

---

## Research Topics

### Automated Market Makers (AMM)

AMMs replace traditional order books with algorithmic liquidity pools.

Topics covered:

- Constant product model (x * y = k)
- Concentrated liquidity (Uniswap V3)
- Impermanent loss
- Liquidity provider incentives

Folder: `/amm`

---

### Lending Markets

DeFi lending protocols enable permissionless borrowing using over-collateralized loans.

Topics covered:

- Lending pool architecture
- Interest rate models
- Borrow utilization curves
- Collateral risk management

Folder: `/lending`

---

### MEV (Maximal Extractable Value)

MEV refers to profit opportunities extracted from transaction ordering.

Topics covered:

- Sandwich attacks
- DEX arbitrage
- Liquidation racing
- Builder / searcher supply chain

Folder: `/mev`

---

### Liquidation Systems

Liquidations protect lending protocols from bad debt.

Topics covered:

- Health factor mechanics
- Oracle price dependency
- Liquidation incentives
- Cascading liquidations during market crashes

Folder: `/liquidation`

---

## Why This Research Matters

DeFi protocols are economic systems built on smart contracts. Understanding their mechanisms is essential for:

- risk analysis
- protocol design
- MEV mitigation
- capital efficiency

This repository aims to provide clear explanations of how these mechanisms interact and where vulnerabilities may emerge.

---

## Future Additions

- Perpetual DEX mechanics
- Liquidity fragmentation
- Protocol-owned liquidity
- Intent-based trading
- Order flow auctions

---

## Resources

Academic papers and protocol documentation used in this research can be found in `/resources`.

---

## Author

Independent DeFi researcher documenting the mechanics behind on-chain financial systems.