## 2025-05-22 - [Dependency Override Strategy for ReDoS]
**Vulnerability:** ReDoS vulnerabilities in `picomatch` (GHSA-c2c7-rcm5-vvqj, GHSA-3v7f-55p6-f55p).
**Learning:** The dependency tree for this repository has a bifurcation for `picomatch`. `micromatch@4.0.8` (used by `lint-staged`) requires the `2.x` branch, while `tinyglobby` (used by `markdownlint-cli@0.48.0`) uses the `4.x` branch. A single global override to `4.0.4` would break `micromatch` compatibility.
**Prevention:** Use nested `overrides` in `package.json` to target specific versions for different branches of the dependency tree (e.g., pinning `picomatch@4.0.4` globally but `2.3.2` specifically under `micromatch`).

## 2025-05-22 - [GitHub Actions Permission Hardening]
**Vulnerability:** Excessive default permissions for GitHub Actions tokens.
**Learning:** Workflows for linting and testing only require `contents: read`. Without explicit `permissions` blocks, the `GITHUB_TOKEN` may have broader access than necessary, increasing the impact of a potential CI compromise.
**Prevention:** Always define a top-level `permissions` block in GitHub Action workflows, defaulting to `contents: read` for standard CI tasks.
