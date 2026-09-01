# Multi-Chain Web3 DevSecOps Template

A reusable security-analysis template for smart-contract projects spanning **Ethereum/Solidity** and **Solana/Rust**.

> Built for security-focused development, automated checks, and repeatable audit workflows.

## What it provides

- Automated security-analysis workflows
- Static analysis and linting integrations
- Secret-detection support
- Fuzzing and property-based testing hooks
- SARIF-compatible security reporting
- Configurable analysis depth and target selection
- Documentation for local and CI-based workflows

## Tooling

| Area | Tools / technologies |
|---|---|
| Ethereum | Solidity, Slither, Mythril, Hardhat |
| Solana | Rust, Anchor, Cargo Audit, Clippy |
| Security | Semgrep, Echidna, Gitleaks |
| Automation | GitHub Actions |

## Repository structure

```text
.
├── .github/          # CI/CD and security workflows
├── contracts/        # Solidity contracts when applicable
├── programs/         # Solana/Anchor programs when applicable
├── tools/            # Security-tool configuration
├── .env.example      # Example environment configuration
├── Dockerfile        # Containerized environment
├── Anchor.toml       # Anchor configuration
└── Cargo.toml        # Rust workspace configuration
```

The exact directories used depend on the project being audited.

## Quick start

```bash
git clone https://github.com/Wonderadroit/solana-devsecops-template.git
cd solana-devsecops-template
```

Review the setup documentation before running workflows:

- `AUTOMATED_SETUP.md`
- `API_KEYS_GUIDE.md`
- `INTEGRATION_GUIDE.md`
- `MULTI_CONTRACT_SETUP.md`

## CI/CD workflow

```text
Code → Build/Test → Static Analysis → Security Checks → Report
```

GitHub Actions can run checks automatically on repository events or manually when deeper analysis is required.

## Security philosophy

Automated scanners are **signals, not proof**. Findings should be reviewed, reproduced where possible, and assessed against the application's actual trust boundaries, invariants, and business logic.

This template does not guarantee vulnerability detection or bug-bounty eligibility.

## Responsible use

Use this tooling only against code and systems you are authorized to assess. Do not test third-party targets without permission.

## Status

An evolving security-engineering template. Configuration and workflow changes are expected as the project develops.

## License

MIT

---

**Author:** [Wonderadroit](https://github.com/Wonderadroit)
