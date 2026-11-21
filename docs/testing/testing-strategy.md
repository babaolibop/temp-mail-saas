# Testing strategy

Use Laravel feature tests at HTTP and module boundaries, unit tests for deterministic actions, and browser checks for accessible interactions and layout. Use fake requirement probes, isolated databases and storage, and synthetic mail fixtures. Keep secret-like values out of committed fixtures and output.

| Area | Required checks |
| --- | --- |
| Installer foundation | GET response with no product database, runtime-check outcomes, secure installed gate, no unreachable Continue action |
| Installer database | Unsupported driver, invalid form, bounded connection failure, redaction, secure persistence and retry |
| Installer administrator | Migration failure, existing accounts, duplicate submission, replay and interruption recovery |
| Completion | Durable lock, restart, denied stale requests, safe completion feedback, parallel attempts |
| Future accounts and authorization | Redirects and intended destinations, guest and owner isolation, resource denial |
| Blade and appearance | Component states and labeling, theme default and persistence, OS changes, disabled and pending controls |
| Accessibility and responsive | Keyboard, screen reader, measured contrast, reduced motion, 320 px reflow, long error strings |
| Production assets | Run Vite build, verify manifest and asset URLs without a development server |
| Mail and storage | Recipient isolation, inert rendering, attachment authorization, intake idempotency and cleanup retries |

Run focused tests followed by the relevant suites with `php artisan test`. For UI changes, verify installer flows in a desktop and narrow browser at the local URL, and run the frontend build. Report commands and outcomes. Documentation-only changes use link checks and diff inspection.

## Observed environment limits

In the previous Codex check, PHPUnit could not bootstrap. PHP could load `vendor/autoload.php` directly while `is_readable()` reported false. The local HTTP socket was restricted and direct GitHub DNS lookup failed. The Laravel skeleton files were untracked. Recheck these observations in the intended execution environment before relying on test, browser, and Git results. Treat launcher or environment failures separately from failed assertions.
