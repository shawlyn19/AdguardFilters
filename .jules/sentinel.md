## 2025-01-24 - [Security] DevDependency Vulnerability Remediation
**Vulnerability:** Multiple ReDoS and command injection vulnerabilities in transitive devDependencies (minimatch, brace-expansion, markdown-it, glob).
**Learning:** Even in a repo that is mostly static content (filter rules), the build/lint toolchain can introduce significant security risks. `npm audit` is a vital tool for identifying these.
**Prevention:** Regularly audit dependencies. Use the `overrides` field in `package.json` to force patched versions of transitive dependencies when direct updates are unavailable or breaking. Document the reason for overrides using a top-level `"//"` key to maintain transparency for future contributors.
