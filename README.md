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

## ZK integration (high level)

The repository includes an `IZKVerifier` interface and an example router contract wired to call a verifier.
Typical integration steps:
1. Build a circuit (e.g., Circom) that outputs a proof + public signals.
2. Generate a verifier contract (e.g., Groth16 verifier) and deploy it.
3. Have your on-chain contracts validate proofs via the verifier interface.

See `circuits/README.md` for guidance and placeholders.

## Scripts

- `npm run compile` — compile contracts
- `npm test` — run tests
- `npm run deploy:local` — deploy to local Hardhat network
- `npm run lint` — run Solhint

## License

MIT — see `LICENSE`.
