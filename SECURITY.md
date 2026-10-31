# Security

- Report vulnerabilities privately to the repository owner; do not open public issues.
- The Firebase Admin credential exists only as a server-side environment variable on the API.
- Firestore rules deny all client writes; every mutation goes through the API, which verifies the
  Firebase ID token and checks project ownership on every request.
- The API applies Helmet headers, a CORS allow-list, rate limiting and Zod input validation.
- Firebase Storage is intentionally not used.
- Run `pnpm audit` regularly (also part of the CI workflow as a non-blocking check).
