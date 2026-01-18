<p align="center">
  <img src="https://i.imgur.com/2PGETZx.jpeg" alt="VeilSwap Banner" />
</p>
<p align="center">
  <a href="https://www.npmjs.com/package/@veilswapapp/sdk">
    <img src="https://img.shields.io/npm/v/@veilswapapp/sdk?color=00e5ff&label=npm&logo=npm" />
  </a>
  <a href="https://www.npmjs.com/package/@veilswapapp/sdk">
    <img src="https://img.shields.io/npm/dm/@veilswapapp/sdk?color=00e5ff&label=downloads" />
  </a>
</p>
# VeilSwap

A starter repository for an EVM smart-contract project with a **clean, production-lean layout** and room to plug in **zero-knowledge (ZK) verification** components.

> Note on privacy: This template focuses on **legitimate privacy-by-design** patterns (e.g., selective disclosure, proving properties without revealing private inputs). It does **not** include tooling intended to conceal illicit fund flows or bypass compliance.

## What's inside

- `contracts/` — Solidity contracts (example: `VeilSwapRouter` + `IZKVerifier` interface)
- `circuits/` — place for ZK circuits (currently scaffolding + docs)
- `scripts/` — Hardhat deploy scripts
- `test/` — basic tests (Hardhat + Chai)
- `.github/workflows/ci.yml` — GitHub Actions CI (lint + test)
- `.env.example` — environment variable template
- Formatting & linting: Prettier + Solhint

## Quick start

### Requirements
- Node.js 18+ recommended
- npm (or pnpm/yarn if you prefer)

### Install & run
```bash
cp .env.example .env
npm install
npm run compile
npm test
```

### Local deploy (Hardhat)
```bash
npm run deploy:local
```
## SDK (npm)

VeilSwap provides a developer-friendly SDK for integrating privacy-preserving swaps into applications and services.

### Installation

    npm install @veilswapapp/sdk

### Usage

    import { veilSwapInfo } from "@veilswapapp/sdk";

    console.log(veilSwapInfo());

### Package

npm: https://www.npmjs.com/package/@veilswapapp/sdk

## ZK integration (high level)

The repository includes an `IZKVerifier` interface and an example router contract wired to call a verifier.
Typical integration steps:
1. Build a circuit (e.g., Circom) that outputs a proof + public signals.
2. Generate a verifier contract (e.g., Groth16 verifier) and deploy it.
3. Have your on-chain contracts validate proofs via the verifier interface.

See `circuits/README.md` for guidance and placeholders.

## Scriptsƒ

- `npm run compile` — compile contracts
- `npm test` — run tests
- `npm run deploy:local` — deploy to local Hardhat network
- `npm run lint` — run Solhint

## License

MIT — see `LICENSE`.
