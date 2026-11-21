# Accessibility

Target WCAG 2.2 AA. Use page landmarks, a skip link when navigation repeats, meaningful headings, native controls, linked labels, and logical keyboard order. Use buttons for actions and links for navigation. Keep focused controls visible behind sticky regions and during scroll. Provide a visible focus outline and verify it in forced colors.

Measure text contrast at 4.5:1 for ordinary text and 3:1 for large text. Measure essential control boundaries and graphical state indicators at 3:1 against adjacent colors where required. Use 44 px default controls and check the WCAG 2.2 target-size criterion for smaller interactive elements. Verify reflow at 320 CSS px and 200% text zoom. Honor reduced motion and allow viewport zoom.

Associate errors with inputs and give form failures a readable summary when needed. Announce dynamically inserted status without stealing focus for routine updates. Accessibility checks must include labels for icon controls, modal focus return, browser autofill, and permissible use of password managers.

Record automated findings plus manual keyboard, screen reader, zoom, and theme checks. Token proposals alone provide no evidence of conformance. See [testing strategy](../testing/testing-strategy.md).
