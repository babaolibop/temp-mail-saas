# Module contracts and ownership

| Planned owner | Owns | Public boundary |
| --- | --- | --- |
| Installer | Requirements checks, setup progression, completion marker | Installation status read contract and installer-only HTTP routes |
| Accounts | Users, credentials, administrator role | Authorized provisioning action and identity queries |
| Mailboxes | Address allocation, owner or guest access, expiry | Address resolution and access decisions |
| Mail | Inbound intake, messages, attachment metadata and private objects | Authenticated delivery intake and authorized mailbox message reads |
| Settings | Application settings and typed defaults | Validated setting reads and authorized updates |

Install calls the Accounts provisioning action only in INSTALL 03/04. Mail resolves a recipient through Mailboxes and writes only mail-owned records. Expiry notifications may trigger cleanup, while worker actions recheck the current expiry and ownership state. Blade and transport layers consume narrowly scoped data from their module.

Contracts should describe inputs, return values, authorization context, common failure cases, and retry guarantees. Pass identifiers and typed data across boundaries. Keep secret-bearing input out of events. Verify module integration with supported entry points and test that callers cannot circumvent authorization by changing resource identifiers.
