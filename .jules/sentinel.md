# Sentinel Security Journal

## 2026-04-20 - [Transitive Vulnerabilities]
**Vulnerability:** Transitive vulnerabilities in `picomatch`, `smol-toml`, `yaml`, and `brace-expansion` were identified via `npm audit`.
**Learning:** Even when top-level devDependencies are pinned, transitive dependencies can introduce security risks such as ReDoS and Denial of Service.
**Prevention:** Use npm `overrides` in `package.json` to explicitly pin secure versions of transitive dependencies and document the GHSA/CVE IDs.
