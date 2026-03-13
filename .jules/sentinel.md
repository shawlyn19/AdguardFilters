# Sentinel Journal 🛡️

This journal records CRITICAL security learnings specific to the AdGuard Filters repository.

## Journal Entries

## 2025-05-14 - Dependency Remediation via Overrides
**Vulnerability:** Multiple high-severity ReDoS vulnerabilities (GHSA-3ppc-4f35-3m26, GHSA-v6h2-p8h4-qcjw, GHSA-38c4-r59v-3vqw), command injection (GHSA-5j98-mcp5-4vw2), and prototype pollution (GHSA-mh29-5h37-fv8m) in transitive dependencies of `markdownlint-cli` and `@adguard/aglint`.
**Learning:** Upgrading direct `devDependencies` often isn't enough to resolve deep transitive vulnerabilities if the intermediate packages haven't been updated. Using the `overrides` field in `package.json` allows for targeted patching of these vulnerabilities without waiting for the entire dependency tree to catch up.
**Prevention:** Regularly audit dependencies with `npm audit` and use version overrides to pin vulnerable transitive packages to secure versions. Maintain exact pinning for security tools to ensure a consistent and secure CI/CD environment.
