# MEV Supply Chain

## Overview

The MEV supply chain describes the ecosystem of participants and infrastructure that enables Maximal Extractable Value (MEV) extraction in blockchain networks. This complex system evolved from simple arbitrage strategies to a sophisticated multi-layered infrastructure involving searchers, builders, relays, and validators.

## Searchers

### Role
- Identify profitable MEV opportunities
- Develop sophisticated strategies and bots
- Submit transaction bundles for inclusion

### Types of MEV
- **Arbitrage**: Cross-DEX price discrepancies
- **Liquidation**: Protocol liquidation opportunities
- **Sandwich attacks**: Front/back-run user transactions
- **Time-bandit attacks**: Reorganize blocks for profit

### Infrastructure
- Mempool monitoring
- Block simulation tools
- High-performance transaction submission
- Proprietary MEV strategies

## Builders

### Function
- Aggregate transactions into blocks
- Optimize for MEV extraction
- Submit blocks to validators

### Competitive Advantages
- Proprietary MEV algorithms
- Network of searchers
- Advanced block construction
- Relationships with validators

### Key Players
- Flashbots
- BloXroute
- MEV-boost relays
- Private builders

## Relays and Validators

### Relay Networks
- Receive bundles from searchers
- Forward to validators
- Manage bundle ordering
- Ensure privacy and fairness

### Validator Participation
- Choose which blocks to propose
- Maximize MEV rewards
- Balance between different builders
- Follow MEV-boost guidelines

### MEV Distribution
- Searchers: Profit from successful extraction
- Builders: Fee for block construction
- Validators: Block rewards + MEV share
- Relay: Service fees

## Order Flow

### Transaction Sources
- Public mempools
- Private transaction relays
- DEX routers
- Cross-chain bridges

### Routing Strategies
- Minimize MEV exposure
- Use private channels
- Optimize for execution price
- Balance privacy and speed

### MEV Minimization
- Flashbots Protect
- Private RPC endpoints
- Transaction batching
- Time-delay mechanisms

## Incentive Alignment

### Economic Balance
- Searchers need sufficient profit margin
- Builders need competitive advantage
- Validators need maximum rewards
- Users need fair execution

### Systemic Risks
- Centralization of MEV extraction
- Validator capture by builders
- Regulatory pressure on MEV
- Protocol-level MEV solutions

## Open Questions

- How will the MEV supply chain evolve with Ethereum upgrades? ([See sandwich attack](../mev/sandwich-attack.md))
- Can decentralized MEV solutions compete with centralized infrastructure? ([See arbitrage](../mev/arbitrage.md))
- What is the optimal distribution of MEV rewards across the supply chain? ([See constant product](../amm/constant_product.md))
