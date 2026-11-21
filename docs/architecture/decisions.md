# Architecture decisions

| Decision | Status | Rationale and consequence |
| --- | --- | --- |
| Laravel 13 and PHP 8.5 | Confirmed | One Laravel runtime and native conventions, with shared hosting checked against the project runtime. |
| Modular monolith | Confirmed | Explicit owners and contracts within one deployable application. |
| Blade, Tailwind CSS, Alpine.js, Vite | Confirmed target | HTML first, local enhancement, compiled production assets. Alpine integration is future work. |
| Comfortable density, Geist, Zinc and Indigo, System initial | Confirmed | Shared visual language and an accessible three-mode appearance. |
| File-backed installer state and durable marker | Proposed | Supports a pre-database flow. Requires private persistent storage and locking. |
| MySQL/MariaDB via PDO MySQL for web setup | Proposed | Matches the shared-hosting target. Verify supported engine versions before implementation. SQLite remains available for isolated tests. |
| Provider or gateway SMTP receipt | Proposed | Inbound SMTP is a separate infrastructure capability, with a verified delivery contract into Laravel. |

Update this register when a proposal becomes an implementation decision. Record compatibility effects and the specifications affected. Keep proposals and observed implementation status explicit in reviews.
