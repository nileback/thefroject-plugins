# /security-scan — Security Scan

Scan the codebase for common security issues.

1. Check for hardcoded secrets (API keys, passwords, tokens)
2. Review authentication and authorization logic
3. Check input validation and sanitization
4. Review dependency vulnerabilities (npm audit, etc.)
5. Check for common OWASP issues (injection, XSS, CSRF)
6. Review file permissions and access control

Output: prioritized list of findings with severity and remediation.

Usage: `/security-scan [optional-directory]`
