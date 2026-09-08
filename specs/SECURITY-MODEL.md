# BOI Security and Access Model

## Principles

1. Treat company documents as sensitive.
2. Do not commit secrets, API keys, passwords, session cookies or credentials.
3. Use environment variables or approved local secret storage.
4. Do not bypass authentication, CAPTCHA, access controls or rate limits.
5. Prefer official/authorized APIs or access mechanisms.
6. Log connector failures without logging secrets.
7. Separate sensitive commercial knowledge from general capability knowledge.
8. Do not send private company documents to external services unless intentionally configured and authorized.
9. Do not automatically submit bids or perform irreversible procurement actions in Phase 1.
10. Maintain provenance for externally retrieved tender information.

## Data handling

The framework should distinguish:
- source data
- derived data
- AI-generated inference
- confidential commercial data

## External connector rule

The BOI connector abstraction must not depend on bypass techniques. If an external source cannot be accessed reliably and legitimately, report the limitation and stop.
