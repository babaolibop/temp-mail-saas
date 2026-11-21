# AGENTS.md

## 1. Project identity and technology baseline

Temp Mail SaaS lives at `C:\Users\ALP\Documents\rip` and is maintained at https://github.com/babaolibop/temp-mail-saas on `main`. The target stack is Laravel 13 and PHP 8.5, with a modular monolith, server-rendered Blade, Tailwind CSS, Alpine.js, and Vite. Use English for user-facing copy.

## 2. Repository conventions

Keep the application directly in the repository root. Follow existing directory, naming, and formatting conventions, including Composer PSR-4 autoloading and Laravel Pint. Keep dependencies, generated files, local secrets, and unrelated formatting outside the diff unless explicitly required. Use Composer and the existing frontend package manager when dependency changes are in scope.

## 3. Mandatory AGENTS and DOCS reading workflow

Before every coding task, Codex must:

1. Read the root `AGENTS.md` and any applicable directory-level guidance.
2. Read `docs/README.md` when available.
3. Read the relevant documentation under `docs/`.
4. Inspect the existing codebase, including entry points, callers, and relevant tests.
5. Implement the requested changes in actual project files.
6. Follow the project’s architecture, security, UI/UX, and accessibility standards.
7. Execute relevant tests and checks.
8. Update affected documentation.
9. Review the Git diff and working-tree status.
10. Commit and push when authorized by the task.
11. Report verified results and any checks that could not run.

Documentation is persistent project guidance. Consult it on each task and keep it synchronized with the implementation. Check PHP and Composer before work that requires them. When a task explicitly includes Laravel Boost setup, use `composer require laravel/boost --dev` and `php artisan boost:install` from the application root, then reread this file and preserve project-specific rules. Governance-only work requires no runtime or dependency installation.

## 4. Laravel and PHP standards

Use typed PHP signatures where they clarify contracts and follow Laravel conventions and installed framework APIs. Keep controllers focused on HTTP concerns. Use Form Requests for nontrivial validation, policies for resource authorization, and focused actions or services for business rules. Use configuration files for environment-dependent values and access those values through Laravel configuration.

## 5. Modular monolith architecture

Deploy one Laravel application. Organize capabilities into modules and document their public entry points and dependencies. Use explicit contracts for cross-module calls and events for genuinely decoupled reactions. Keep dependency direction explicit and avoid cycles or direct writes to another module’s data.

## 6. Module boundaries and ownership

Each module owns its routes, requests, actions, policies, models, migrations, views, and tests where applicable. Name the owner of shared data and route mutations through that owner. Scope routes and views clearly so module names do not collide. Follow documented registration and directory conventions.

## 7. Shared services and component conventions

Place genuinely shared infrastructure and components in the existing shared layer. Keep domain rules in their owning modules. Reuse Blade components for controls, forms, alerts, navigation, and layout primitives. Define clear props and slots, preserve native semantics, and use Alpine for local interaction state.

## 8. Security requirements

Validate and authorize all privileged operations server-side, including ownership and tenant isolation where applicable. Keep Laravel CSRF protection on state-changing web routes, escape Blade output by default, and render untrusted email content through a deliberately isolated, sanitized view. Use parameterized queries, protect against mass assignment, and rate-limit abuse-prone endpoints. Keep credentials, mailbox tokens, and message contents out of logs and source control. Test access-control and failure paths affected by changes.

## 9. Database and migration practices

Keep migrations versioned and compatible with supported deployment databases. Preserve existing data and use additive changes or staged migrations for risky schema changes. Separate large backfills from schema changes when needed. Use constraints and indexes for actual invariants and query patterns. Use transactions for related writes, and handle retries or concurrent execution without duplicating effects. Test migration and rollback behavior where applicable.

## 10. Premium SaaS design philosophy

Use Linear for precision, spacing, and alignment, Stripe for forms and feedback, Vercel for minimal SaaS layouts, GitHub for functional navigation and accessibility, and Vite for visual clarity. Use these references to guide decisions while developing an original visual identity. Keep density comfortable and prioritize the current user task.

## 11. Brand identity and logo standards

Create a distinct, professionally designed identity with consistent typography, color, iconography, and tone. A generic stock icon requires design review before it can be accepted as the final logo. Review marks for legibility at small sizes, theme variants, and monochrome use. Document approved logo variants and usage.

## 12. Design tokens and UI components

Use Geist typography, Zinc 50–950 neutral colors, and a controlled Indigo accent. Centralize semantic tokens for surface, text, border, focus, status, spacing, and control dimensions. Provide Light, Dark, and System modes, with System as the initial preference. Respect OS changes in System mode and persist explicit choices. Reuse component variants and align control heights, typographic scales, and spacing.

## 13. Responsive design

Design mobile-first and verify layouts at narrow, intermediate, and desktop widths. Preserve primary actions, reading order, and keyboard access as navigation and forms reflow. Support long email addresses and localized-length text without clipping or page overflow.

## 14. Accessibility

Target WCAG 2.2 AA. Use semantic landmarks, programmatic labels, keyboard operation, visible and unobscured focus, sufficient contrast, and accessible target sizes. Honor reduced motion. Give icon-only controls accessible names and communicate errors and status through text. Verify both themes and keyboard navigation for affected flows.

## 15. Interaction and form UX

Use persistent labels and concise instructions. Link field errors to their controls, preserve safe input on validation failure, and provide clear loading, success, and failure states. Support autofill and password managers. For password fields, use a shared accessible show/hide control and a Caps Lock indicator where applicable. Guard duplicate submissions while preserving clear retry behavior.

## 16. Testing and regression prevention

Use Laravel feature tests for user journeys, module boundaries, authorization, and validation. Use unit tests for business rules and browser checks for interaction or visual changes. Cover applicable failure paths, existing data, and regressions. Run targeted tests first, then affected suites, frontend builds, and formatting checks as warranted. Report exact commands and results.

## 17. Performance and shared-hosting requirements

Keep Blade as the rendering baseline, limit JavaScript, prevent N+1 queries, paginate large collections, and bound background work. Build Vite assets before production deployment so the server does not require a Node runtime. Keep the public document root at `public/`. Document PHP extensions, database, writable directories, scheduling, and queue requirements, including bounded execution on hosting without persistent workers.

## 18. Documentation synchronization

Update the relevant documents when architecture, configuration, deployment, module contracts, data, or user flows change. Keep `docs/README.md` aligned when documents are added or moved. Record decisions and the verification or migration steps needed to maintain the affected area.

## 19. Git workflow

Verify the repository root, remote, branch, and working-tree status. Preserve existing user changes, stage task files explicitly, review the staged diff, and use descriptive commits. Commit and push only with task authorization. Use a non-force push to the verified destination, and verify the resulting branch head remotely. Report conflicts or rejected updates without rewriting history or discarding work.

## 20. Definition of Done

The requested files exist and work through their normal entry points. Relevant behavior, security, and accessibility checks are complete or explicitly reported as blocked. Documentation reflects the change. The diff contains only authorized work and passes applicable checks. When publishing is authorized, the commit and remote state are verified. The final report identifies the deliverable, exact verification results, and any remaining limitations.
