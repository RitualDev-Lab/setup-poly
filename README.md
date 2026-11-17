# Setup Poly GitHub Action ⚡

> Set up your GitHub Actions workflow with the **Poly Universal Polyglot Package & Dependency Orchestrator** for Node.js, Python, Rust, and Go.

[![CI](https://github.com/RitualDev-Lab/setup-poly/actions/workflows/ci.yml/badge.svg)](https://github.com/RitualDev-Lab/setup-poly/actions)
[![npm version](https://img.shields.io/npm/v/@ritualdev-lab/poly.svg?color=blue)](https://www.npmjs.com/package/@ritualdev-lab/poly)

---

## Features

- ⚡ **Zero-Friction Setup**: Installs `@ritualdev-lab/poly` globally on GitHub Actions runners (`ubuntu-latest`, `macos-latest`, `windows-latest`).
- 📦 **Automated Dependency Caching**: Caches and restores `node_modules`, Python virtual environments (`.venv`), and Rust build artifacts (`target`) using deterministic `poly.lock` cryptographic hash keys.
- 🛡️ **Zero-Drift CI Enforcer**: Run `poly install --frozen` or `poly audit --fail-on high` directly in your CI pipeline.

---

## Usage

### Basic Usage

```yaml
steps:
  - name: Checkout repository
    uses: actions/checkout@v4

  - name: Set up Node.js
    uses: actions/setup-node@v4
    with:
      node-version: '22'

  - name: Set up Poly
    uses: RitualDev-Lab/setup-poly@v1
    with:
      version: 'latest'

  - name: Install & synchronize polyglot dependencies
    run: poly install --frozen

  - name: Audit cross-stack vulnerabilities
    run: poly audit --fail-on high
```

### Specifying Version & Disabling Cache

```yaml
- name: Set up Poly (v0.1.0 without cache)
  uses: RitualDev-Lab/setup-poly@v1
  with:
    version: '0.1.0'
    cache: 'false'
```

---

## Action Inputs

| Input | Description | Required | Default |
|---|---|---|---|
| `version` | Version of `@ritualdev-lab/poly` to install | No | `latest` |
| `cache` | Automatically restore dependency cache based on `poly.lock` | No | `true` |
| `cache-dependency-path` | Path to composite lockfile | No | `poly.lock` |

## Action Outputs

| Output | Description |
|---|---|
| `poly-version` | Installed `poly` CLI version |

---

## License

MIT © [RitualDev Lab](https://ritualdev.in)

---

---

## 💖 Sponsor & Support

If you find this project valuable, consider supporting our open-source development:

[![Sponsor on Dodo Payments](https://img.shields.io/badge/Sponsor_via_Dodo-Payments-8b5cf6?style=for-the-badge&logo=shield&logoColor=white)](https://checkout.dodopayments.com/buy/pdt_0NpjONGugY5QkrFDUaPva)
[![Interactive Donation Portal](https://img.shields.io/badge/Donation_Portal-Cards%20%7C%20UPI%20%7C%20Apple%20Pay-ff5964?style=for-the-badge&logo=heart&logoColor=white)](https://ritualdev.in/donate)
[![GitHub Sponsors](https://img.shields.io/badge/GitHub_Sponsors-RitualDev--Lab-ea4aaa?style=for-the-badge&logo=githubsponsors&logoColor=white)](https://github.com/sponsors/RitualDev-Lab)

- [**⚡ 1-Click Dodo Payments Checkout**](https://checkout.dodopayments.com/buy/pdt_0NpjONGugY5QkrFDUaPva)
- [**🎁 Interactive Donation Portal**](https://ritualdev.in/donate)
- [**❤️ GitHub Sponsors**](https://github.com/sponsors/RitualDev-Lab)

---

## 🛡️ Community & Governance
- [Code of Conduct](CODE_OF_CONDUCT.md)
- [Contributing Guidelines](CONTRIBUTING.md)
- [Security Policy](SECURITY.md)
- [Accessibility Statement](ACCESSIBILITY.md)
- [License](LICENSE)
