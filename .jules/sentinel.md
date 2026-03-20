## 2025-05-15 - Hardening GitHub Actions
**Vulnerability:** GitHub Actions workflows were using mutable tags and lacked explicit permissions, posing a supply chain risk and violating the principle of least privilege.
**Learning:** Pinning to commit SHAs ensures immutability, but requires manual updates to keep actions secure. Explicit permissions limit the impact of a compromised action.
**Prevention:** Always define `permissions` at the workflow or job level and pin third-party actions to verified commit SHAs.

## 2025-05-15 - CI Execution Blocked by Billing
**Vulnerability:** CI jobs failing to start with "account is locked due to a billing issue".
**Learning:** This is an infrastructure/account-level issue in GitHub that cannot be resolved by code changes.
**Prevention:** Monitor GitHub account status and billing; ensure the runner environment is healthy before attributing CI failures to code changes.
