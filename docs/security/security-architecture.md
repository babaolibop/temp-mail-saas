# Security architecture

Use server-side validation, session separation, authorization policies and owner-scoped resource lookups. Enforce authorization for each operation, including downloads, worker paths, and route-model binding. Use Laravel CSRF protection for browser mutations, default Blade escaping, parameterized queries, and explicit mass-assignment boundaries. Regenerate session identifiers after privilege changes. Use HTTPS, secure HttpOnly cookies, appropriate SameSite settings, and trusted-proxy configuration that matches hosting.

Treat installer access as privileged from first exposure. Gate setup before public routing, validate every transition, serialize writes, and block re-entry using the durable marker. Rotate or remove the setup access credential after finalization. Apply rate limits to setup attempts, registration when implemented, mailbox allocation, reads, and inbound delivery using appropriate keys and shared state in production. Give connection attempts verified timeouts and restrict destinations to operator-approved database hosts.

Keep secrets outside public paths and repository history. Provision environment values through hosting secrets or a restricted environment file. Use Laravel password hashing for human credentials. Store only digests of high-entropy bearer tokens where lookup permits. Keep tokens, credentials, mail bodies and attachment content out of routine logs and error responses. Use redacted structured security events and constrained log access and retention.

Treat inbound events and messages as separate trust boundaries. Authenticate intake, enforce quotas, and use [email safety](email-safety.md) for rendering and downloads. Test authorization denial, isolation, secret redaction, and abuse limits using synthetic data.
