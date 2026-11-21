# Project documentation

Temp Mail SaaS provides time-limited inboxes for receiving email. The target baseline is Laravel 13, PHP 8.5, server-rendered Blade, Tailwind CSS, Alpine.js, and Vite. One Laravel deployment hosts modules with explicit ownership and contracts. User-facing text is English.

## Start here

Before implementing any feature, read root [AGENTS.md](../AGENTS.md), this index, and the relevant architecture, security, frontend, and testing specifications. Inspect the existing code and tests before changing files. Use the documents to guide implementation and verification. Update impacted specifications and this index when behavior, paths, or decisions change. Review the diff and report verified results.

## Specifications

- Architecture — [Overview](architecture/overview.md), [Modular monolith](architecture/modular-monolith.md), [Module contracts](architecture/module-contracts.md), [Decisions](architecture/decisions.md).
- Installer — [Architecture and phases](installation/installer-architecture.md), [Installer UX](installation/installer-ux.md).
- Frontend — [Design system](frontend/design-system.md), [Tokens](frontend/design-tokens.md), [Components](frontend/components.md), [Accessibility](frontend/accessibility.md), [Responsive layout](frontend/responsive.md).
- Branding — [Identity](branding/brand-identity.md), [Logo](branding/logo-specification.md).
- Security — [Security architecture](security/security-architecture.md), [Email safety](security/email-safety.md).
- Backend and delivery — [Database](database/database-architecture.md), [Mail](mail/mail-architecture.md), [Testing](testing/testing-strategy.md), [Shared hosting](deployment/shared-hosting.md).

## Development order and status

Repository governance precedes this documentation. Implement and verify INSTALL 01/04 through INSTALL 04/04 in order. Discuss later features after the installer is verified and their scope is authorized.

Laravel 13 and the local PHP 8.5 runtime are observed. The stack, design direction, accessibility target, and phase order are confirmed requirements. Module directories, schemas, installer routes, component APIs, and token values below are proposed implementation contracts. The current local Laravel skeleton has a welcome route and example tests. The installer, reusable UI system, and mail pipeline are planned.
