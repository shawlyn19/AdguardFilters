# Sentinel Security Journal

🛡️ Sentinel mission: Identify and fix ONE small security issue or add ONE security enhancement.

## 2025-05-15 - [Vulnerability remediation via dependency overrides]

**Vulnerability:** Multiple vulnerabilities in transitive dependencies (picomatch, brace-expansion, smol-toml, yaml).
**Learning:** Some security reviews may falsely claim versions don't exist; verify using `npm view` directly.
**Prevention:** Use `overrides` in `package.json` to pin transitive dependencies to secure versions.
