# JWT Skills

Agent skills for decoding, encoding, and validating JSON Web Tokens.

## Skills

- **jwt-decode** — Decode and inspect JWTs without verification. Shows header, payload, claims, and flags security issues like `alg: none` or missing expiration.
- **jwt-encode** — Create and sign JWTs for testing and development. Supports HMAC, RSA, and ECDSA algorithms.
- **jwt-validate** — Verify JWT signatures and validate claims. Supports shared secrets, PEM keys, and JWKS endpoints.

## Install

```bash
npx skills add jsonwebtoken/jwt-skills
```

Install a specific skill:

```bash
npx skills add jsonwebtoken/jwt-skills -s jwt-decode
```

## Usage

Once installed, the skills activate automatically when relevant. You can also invoke them directly:

```
/jwt-decode eyJhbGciOiJIUzI1NiIs...
/jwt-encode {"sub": "1234567890", "name": "Test User"}
/jwt-validate eyJhbGciOiJIUzI1NiIs...
```

## Security

These skills handle potential sensitive data (tokens, secrets, keys). They follow these principles:

- Secrets are passed via inline environment variables, never as literal command-line arguments
- Packages are never installed without user consent
- `alg: none` tokens are always flagged as a security risk
- Signature verification never trusts the token's `alg` header (prevents algorithm confusion attacks)
- Sensitive data in payloads is flagged (JWTs are encoded, not encrypted)

## Get Started with JSON Web Tokens

Securely implement authentication with JWTs using Auth0 on any stack and any device in less than 10 minutes.
Create a free account at [auth0.com/signup](https://auth0.com/signup/?utm_source=jwt.io&utm_medium=microsites&utm_campaign=devn_signup)

## Disclaimer

These skills are powered by AI agents, which can make mistakes. Always double-check the output before using tokens or validation results in production or security-sensitive contexts.

## License

Copyright 2026 Okta, Inc.

Licensed under the Apache License, Version 2.0 (the "License"); you may not use this file except in compliance with the License. You may obtain a copy of the License at: [http://www.apache.org/licenses/LICENSE-2.0](http://www.apache.org/licenses/LICENSE-2.0)
