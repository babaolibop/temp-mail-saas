# Database architecture

The following is planned. The local Laravel skeleton already has default user, cache, and job migrations. Review existing migrations before introducing module-owned schema.

| Dataset | Owner | Proposed keys and lifecycle |
| --- | --- | --- |
| Users | Accounts | Primary key, unique normalized email, hashed password and role representation. Privileged provisioning uses a replay-safe setup identity. |
| Mailboxes | Mailboxes | Unique canonical address and optional owner FK; guest-access digest where used; index expiry and owner plus expiry. |
| Messages | Mail | Mailbox FK, received and expiry timestamps, unique intake key per mailbox, index mailbox plus received time and stable tie-break identifier. |
| Attachments | Mail | Message FK, opaque storage key, bounded metadata; index message FK, unique storage reference where appropriate. |
| Installation state | Installer | Private files are authoritative before and after database bootstrap. An optional database audit record may record completed setup with a unique operation ID. |
| App settings | Settings | Unique validated key, typed value and modification metadata. Keep deployment secrets in restricted configuration. |

Enforce primary and foreign keys and explicit deletion behavior. Use UTC timestamps, normalize addresses according to configured domain rules, and confirm collation behavior for unique keys. Enforce expiry in reads before background deletion. Purge in bounded batches using expiry indexes. Delete private objects through retryable operations and reconcile orphaned files. Derive retention limits from product policy and account for backup copies.

Prefer additive migrations, backup before risky changes, and separate long backfills. Account for database-specific DDL transaction behavior. Test real-engine uniqueness, concurrency, and migration recovery where SQLite cannot model production behavior.
