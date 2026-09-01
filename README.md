# Multi-Chain Web3 DevSecOps Template

A reusable security-engineering template for smart-contract projects spanning **Ethereum/Solidity** and **Solana/Rust**.

> Built for security-focused development, automated checks, and repeatable analysis workflows.

## Capabilities

- Static analysis and linting integrations
- Secret-detection support
- Fuzzing and property-based testing hooks
- SARIF-compatible reporting
- Configurable analysis depth and target selection
- Local and CI-oriented workflows
- Multi-chain Rust/Solidity validation

## Tooling

| Area | Tools / technologies |
|---|---|
| Ethereum | Solidity · Slither · Mythril · Hardhat |
| Solana | Rust · Anchor · Cargo Audit · Clippy |
| Security | Semgrep · Echidna · Gitleaks |
| Automation | GitHub Actions |

## Validation model

```text
Source → Build/Test → Static Analysis → Security Checks → Reports → Human Review
```

The repository separates **gating validation** from **security-analysis reporting**. Baseline CI checks project integrity, while the security audit workflow produces findings for review without pretending that automated scanners prove an audit is complete.

## Repository structure

```text
.
├── .github/          # CI/CD and security workflows
├── contracts/        # Solidity contracts and security fixtures
├── programs/         # Solana/Anchor programs
├── fuzz/             # Fuzzing configuration and targets
├── docs/             # Engineering and security documentation
├── .env.example      # Example environment configuration
├── Dockerfile        # Containerized environment
├── Anchor.toml       # Anchor configuration
└── Cargo.toml        # Rust workspace configuration
```

## Quick start

```bash
git clone https://github.com/Wonderadroit/solana-devsecops-template.git
cd solana-devsecops-template
```

Review the repository documentation before running workflows:

- `AUTOMATED_SETUP.md`
- `API_KEYS_GUIDE.md`
- `INTEGRATION_GUIDE.md`
- `MULTI_CONTRACT_SETUP.md`
- `PIPELINE_ASSESSMENT.md`

## Security posture

Security automation is treated as an engineering aid, not an oracle. Findings require contextual review, reproduction, and understanding of application behavior and trust boundaries.

The public portfolio intentionally does **not** include an automatic workflow that generates exploit contracts from scanner findings. Security testing remains focused on authorized analysis, validation, and reproducible reporting.

Use the tooling only against code and systems you are authorized to assess.

## CI and workflow security

Workflows use read-only repository permissions where possible and are designed to separate validation from reporting. See GitHub's [Actions security guidance](https://docs.github.com/en/actions/how-tos/secure-your-work) for workflow-hardening practices.

## Status

**Active development.** Workflow configuration and supported analysis paths may change as the project evolves.

## Contributing

Contributions should include a clear explanation of the change, relevant tests or validation, and any security implications. See `CONTRIBUTING.md` for project expectations.

## License

MIT

---

**Author:** [Wonderadroit](https://github.com/Wonderadroit)
