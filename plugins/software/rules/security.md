---
description: Security practices and vulnerability prevention
---

# Security Rules

- Never hardcode secrets, API keys, or credentials — use environment variables
- Validate and sanitize all user input at system boundaries
- Use parameterized queries — never concatenate user input into SQL
- Escape output in templates to prevent XSS
- Apply principle of least privilege for file and API permissions
- Never commit .env files or credentials to version control
- Use HTTPS for all external API calls
- Log security-relevant events but never log sensitive data (no passwords, tokens, PII in logs)

**Examples of violations:**
- `const apiKey = "sk-abc123"` → use `process.env.API_KEY`
- `db.query("SELECT * FROM users WHERE id=" + userId)` → use parameterized query
- `innerHTML = userInput` → use `textContent` or sanitize first
- `.env` in git → add to `.gitignore`, use `.env.example` with placeholders
