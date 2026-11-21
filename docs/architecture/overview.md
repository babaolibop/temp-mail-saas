# Architecture overview

Use one deployable Laravel 13 application with server-rendered Blade and progressively enhanced Alpine interactions. Build CSS and JavaScript with Vite. Route installation and product workflows through separately owned modules with explicit contracts. Keep the database and private attachment storage behind Laravel adapters.

## Request and data boundaries

- Browser requests pass through Laravel middleware, application validation and authorization, then module actions. Controllers shape responses and delegate business decisions.
- An inbound mail provider or SMTP gateway handles MX receipt and forwards authenticated delivery events. Laravel accepts normalized deliveries through the mail intake boundary. The web host runs the application and private storage adapters.
- Installer checks run before a working product database is assumed. Persistence and shutdown of installer access follow the [installer state machine](../installation/installer-architecture.md).
- Mailbox lifetime and message access are enforced in domain queries and policies. Scheduled cleanup removes expired resources after they are unavailable to users.

See [module conventions](modular-monolith.md), [ownership and contracts](module-contracts.md), and [security](../security/security-architecture.md).
