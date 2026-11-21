# Installer UX

Use a centered layout with the product identity, a theme control, a single step heading, and one content surface. On small screens use one column. Reduce decorative chrome before reducing control size. Use English labels: System Requirements, Database Setup, Administrator Setup, and Complete. A shared ordered step list may show planned steps without links and uses `aria-current="step"` on the current item. Expose review as part of administrator setup.

Display a semantic list of checks with an understandable name, text status, and short corrective action when needed. Use icons as secondary cues. Keep the primary action aligned with fields and use the shared 44 px default control height. In Foundation, omit navigation to unavailable steps. Once connected, present a disabled native button only when the nearby explanation gives an actionable condition. On mobile, stack actions in logical order.

On submission, indicate pending progress in text, prevent duplicate activation, and restore the action after a recoverable failure. Focus the error summary or first invalid control on failed submissions and link summary items to their fields. Preserve safe values, omit passwords from repopulation, and let operators retry. On full page transitions place the current step heading early in the reading order. Never expose paths, secrets, or raw connection errors.

Use Light, Dark, and System with System selected initially. Verify keyboard navigation, visible focus, long error text, status announcements, and normal reflow against the [component](../frontend/components.md), [accessibility](../frontend/accessibility.md), and [responsive](../frontend/responsive.md) contracts.
