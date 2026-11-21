# Modular monolith conventions

Place new capabilities under `app/Modules/<Module>/` with namespace `App\\Modules\\<Module>`. The first planned module is Installer. Create directories as needed.

~~~text
app/Modules/Installer/
  InstallerServiceProvider.php
  routes/web.php
  Http/Controllers/
  Http/Requests/
  Actions/
  Contracts/
  Models/
  Database/Migrations/
  resources/views/
tests/Feature/Modules/Installer/
tests/Unit/Modules/Installer/
~~~

Register a module provider explicitly in `bootstrap/providers.php`. Register bindings in its `register()` method and namespaced views and owned migrations in `boot()`. Load the module route file once through the application web route entry so middleware runs once. Give routes an explicit module name prefix, such as `installer.`; use `installer::requirements` for module views. Verify with route listing and route-cache smoke checks.

Keep HTTP concerns in controllers, input and request-specific authorization in Form Requests, and repeatable business rules in typed actions. Use policies for resource authorization and Laravel transactions where a module owns a multi-write operation. Keep domain models and migrations with their owner. Review migration ordering across modules with foreign keys.

Keep shared Blade primitives under the application component namespace. Keep genuinely shared technical adapters in a small infrastructure layer. Modules may depend on shared infrastructure and declared contracts. Shared code must remain independent of feature modules. Use explicit synchronous contracts for required results and events for independent reactions. Avoid dependency cycles, global service locators, and cross-module writes.
