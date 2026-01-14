# Circuits

This folder is a placeholder for your ZK circuits and related artifacts.

## Suggested layout

- `circuits/` — circuit source files (e.g., `.circom`)
- `build/` — generated artifacts (witness calculators, proving/verifying keys, etc.)
- `scripts/` — helpers to compile circuits and generate proofs
- `verifier/` — generated on-chain verifier contracts (or references to them)

## Typical workflow (example)

1. Write a circuit (Circom or another framework).
2. Compile the circuit and generate keys.
3. Generate a Solidity verifier contract.
4. Deploy the verifier and plug its address into your contracts.

## Important notes

- Keep proving keys and other heavy artifacts out of Git if they are large.
- Be mindful of security: version pinning, audited libraries, and reproducible builds.
