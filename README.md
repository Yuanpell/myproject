# Agent Reputation Hub V2 (BNB Chain Agent ID dApp)

A lightweight, Sybil-resistant on-chain reputation, daily check-in, and peer-to-peer tipping dApp built natively around **SPACE ID Agent ID** on **BNB Smart Chain (BSC)** for the **Binance Wallet Agent ID Hackathon**.

## 🌟 Key Features

1. **Zero-Friction Agentic Wallet Verification & Activation (V2 Upgrade)**
   - Solves the isolated wallet UX bottleneck: users can connect **any standard Web3 wallet** (Binance Wallet, MetaMask, OKX Wallet) to pay gas and activate/check-in on behalf of their isolated **Agentic Wallet (`0x...`)**.
   - Enforces strict on-chain Sybil resistance by verifying `IAgentID(0x60B9262456dE011F7d15a54CdD8c48bAaa8B022F).balanceOf(agentWallet) > 0` before any state mutation.
2. **Read-Only Agent ID & Reputation Lookup**
   - Instant, signature-free lookup for any BSC wallet address to inspect Agent ID holdings, activation status, check-in count, and total BNB tips received.
3. **On-Chain Role Registration & Daily Check-Ins**
   - Agent ID holders register a custom on-chain AI agent persona (`1–32 bytes`) and build verifiable on-chain reputation through 12-hour interval check-ins.
4. **Peer-to-Peer Agent Tipping & Real-Time Activity Feed**
   - Non-custodial 0% fee BNB tipping (`tipAgent`) directly to registered Agentic Wallets, paired with a live leaderboard and BscScan-verifiable transaction log.

## 📜 Smart Contract (BSC Mainnet)

- **Contract Name**: `AgentReputationHubV2`
- **Network**: BNB Smart Chain Mainnet (`Chain ID: 56`)
- **Contract Address**: [`0x1b7073a0D64eA43a2F33bdBb525682E423CA13Ea`](https://bscscan.com/address/0x1b7073a0D64eA43a2F33bdBb525682E423CA13Ea#code)
- **Official Agent ID Reference**: `0x60B9262456dE011F7d15a54CdD8c48bAaa8B022F`

## 🚀 Quick Start

This project uses a zero-build, single-file frontend architecture (`index.html`) powered by `ethers.js v6`:

1. Clone this repository or download `index.html`.
2. Open `index.html` in any Web3-enabled browser or deploy directly to static hosting (Netlify, Vercel, GitHub Pages).
3. Enter your **Agentic Wallet** address in the lookup bar to verify eligibility, connect your main wallet for gas, and click **Activate**.

## 🔒 Security Design

- **Non-Custodial**: The smart contract holds zero user funds; P2P tips transfer directly to the recipient Agentic Wallet following the Checks-Effects-Interactions (CEI) pattern.
- **Operator Binding**: First-time activation binds the calling operator wallet to prevent unauthorized profile overwrites.
- **XSS Protection**: All user-submitted on-chain strings are HTML-escaped prior to DOM rendering.
