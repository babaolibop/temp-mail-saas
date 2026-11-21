# Untrusted email and attachment safety

Treat headers, addresses, bodies, metadata, and attachments as attacker-controlled. Bound raw size, decoded size, MIME nesting, part count, attachment count, and processing time. Normalize malformed input to safe errors. Display sender information as a claim in the message and avoid implying precisely verified identity where none exists.

Default to escaped plain text. If rich display is enabled later, sanitize with a maintained allowlist and render in a sandboxed isolated view with restrictive content policy. Disable scripts, forms, embedded active content, and automatic remote requests or tracking pixels. Keep the parent document and application origin isolated from message markup. Permit only approved URL schemes, and make intentional navigation explicit.

Store attachments in private storage using server-generated identifiers. Treat filenames and media types as untrusted, prevent traversal, enforce limits, and serve download responses with attachment disposition and anti-sniffing headers. Refuse or quarantine disallowed types per policy. Recheck mailbox ownership and expiry on every download. Use short-lived access where direct storage links are necessary.

Tests should cover malformed MIME, size and part limits, hostile HTML held inert, blocked remote resources, filename handling, and denial for another mailbox or an expired message.
