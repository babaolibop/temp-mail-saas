# Mail architecture

An external SMTP service or gateway owns MX records, SMTP reception, buffering, and delivery retries. Laravel is the HTTP application that receives authenticated provider deliveries, authorizes browser access, and manages storage and expiration. Select and verify the provider, DNS arrangements, and delivery contract before enabling public inbound mail.

1. Allocate an address with an approved domain and cryptographically random local identifier. Enforce uniqueness in storage and rate-limit creation. Keep mailbox address separate from authorization credentials.
2. Resolve inbound recipients using provider envelope data. Verify delivery authenticity, freshness and replay controls before accepting work. Apply global, domain and mailbox quotas and enforce message limits.
3. Retain a provider-scoped delivery identity per recipient. Queue bounded parsing work where available. Acknowledge according to the provider retry contract only after durable acceptance or an intentional permanent rejection.
4. Parse safely, store canonical metadata and message content by mailbox, and write attachments to private storage. Keep replays idempotent and reconcile partial storage writes.
5. Recheck owner or guest authorization and expiry for list, read and download. Use safe rendering from [email safety](../security/email-safety.md).
6. Expiry immediately denies reads and new deliveries. Bounded cleanup deletes records and blobs with retry tracking. Verify retention policy, storage quotas, and orphan reconciliation.

Monitor intake failures, lag, quota pressure, and cleanup with redacted telemetry. Verify multi-recipient processing, duplicate events, expired addresses, and partial failures through the public contracts.
