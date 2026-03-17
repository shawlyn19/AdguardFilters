## 2025-05-24 - [Security Enhancement] Update GitHub Actions to latest versions
**Vulnerability:** Use of outdated GitHub Actions versions (v4) which might rely on older, potentially vulnerable Node.js runtimes.
**Learning:** Maintaining CI/CD infrastructure is a key part of defense-in-depth. Using the latest stable versions of common actions like `actions/checkout` (v6) ensures that the automation runs on modern, supported Node.js versions (Node 24) and benefits from the latest security patches and features.
**Prevention:** Regularly audit and update GitHub Action versions. Standardizing on the latest major versions across all workflow files reduces technical debt and security risk.
