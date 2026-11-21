# Blade component contracts

Proposed components use the `x-ui.*` namespace, a shared attribute bag, documented variants, and slots for visible content. Controls default to 44 px and align with 36/48 px variants when grouped. Use the same semantic tokens in every theme and responsive layouts without changing reading order.

| Component | Proposed API and behavior |
| --- | --- |
| Button | `size, variant, type, disabled, loading`. Primary, secondary, and danger variants. Native button, visible pending label, duplicate-submit guard. |
| Icon button | `label, size, pressed`. Accessible name and state, independent target size, visible focus. |
| Text input | `id, name, type, autocomplete, value, invalid`. Preserve autofill and native text editing. |
| Password input | `id, name, autocomplete`. Named show/hide button, Caps Lock feedback while relevant, no password repopulation. |
| Select | `id, name, invalid` and option slot. Native select keyboard controls. |
| Checkbox and radio | `id, name, value, checked`. Linked label, grouped radios use fieldset and legend. |
| Field | `label, for, hint, error, required` and control slot. Stable hint/error IDs wired through `aria-describedby`. |
| Alert | `tone, title` and body slot. Text conveys state. Use assertive announcement only for urgent dynamic errors. |
| Toast | `tone, dismissible` and message slot. Use a polite live region for routine feedback. Keep essential errors in the page. |
| Card and badge | Card header/body/footer slots and badge `tone`. Use headings and text labels as appropriate. |
| Table | Caption, header, and row slots. Semantic headers and a labeled scroll region if overflow is essential. |
| Navigation | Label and link slots, active route with `aria-current`. Responsive disclosure returns focus naturally. |
| Dialog | `id, title`, body and action slots. Trap focus when modal, close via Escape where appropriate, and restore trigger focus. |
| Dropdown | Trigger and content slots. Use disclosure for links. Implement menu semantics and arrow keys only for true action menus. |
| Empty state | `title`, optional body and action slots. Explain the next available action. |
| Loading indicator | `label` and decorative spinner. Set busy state on the affected region and honor reduced motion. |

Define default, hover, focus, disabled, loading, and invalid styles where applicable. Use native disabled controls for unavailable actions and keep contextual reasons visible. Make error text and field state available without color. Test keyboard operation, theme parity, wrapping, and action alignment before reuse.
