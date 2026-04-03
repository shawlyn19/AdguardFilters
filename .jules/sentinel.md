## 2025-05-22 - [GitHub Actions Hardening]
**Vulnerability:** GitHub Actions workflows running with default (overly permissive) GITHUB_TOKEN permissions.
**Learning:** Default permissions for GITHUB_TOKEN can include write access to various scopes, which poses a risk if an action is compromised or a malicious pull request is merged.
**Prevention:** Explicitly define the `permissions` block at the top level of each workflow file to enforce the principle of least privilege. For example, use `contents: read` for linting and `issues: write` only when necessary for automated issue management.
