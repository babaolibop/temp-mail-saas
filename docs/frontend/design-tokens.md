# Design tokens

These are proposed semantic mappings. Measure colors on their real backgrounds for all relevant states before accepting them.

| Role | Light | Dark |
| --- | --- | --- |
| Canvas | Zinc 50 | Zinc 950 |
| Surface | White | Zinc 900 |
| Raised surface | White | Zinc 800 |
| Text | Zinc 950 | Zinc 50 |
| Muted text | Zinc 600 | Zinc 400 |
| Decorative border | Zinc 200 | Zinc 800 |
| Essential control border | Zinc 500 | Zinc 500 |
| Primary action | Indigo 700 with white text | Indigo 400 with Zinc 950 text |
| Focus ring | Indigo 600 | Indigo 400 |
| Success text | Emerald 800 | Emerald 300 |
| Warning text | Amber 900 | Amber 300 |
| Error text | Red 800 | Red 300 |

Use the full Zinc 50–950 scale for neutrals and controlled Indigo for emphasis. Keep state tokens semantic and pair status color with text. Record measured WCAG results when components are implemented.

| Token family | Proposed scale |
| --- | --- |
| Geist type size/line height | 12/16 metadata, 14/20 labels, 16/24 body, 20/28 section, 28/36 page |
| Spacing in px | 4, 8, 12, 16, 24, 32, 48, 64 |
| Radius in px | 6 small, 8 controls, 12 surfaces, full for pills |
| Controls in px | 36 compact, 44 comfortable default, 48 large |
| Icons in px | 16 secondary, 20 controls, 24 feature |
| Containers in rem | 36 form, 72 shell |
| Focus | 2 px ring and 2 px offset, with a visible forced-colors fallback |
| Elevation | Border on cards, subtle shadow on elevated overlays |
| Motion | 120 ms feedback and 180 ms overlays, reduced to instant where motion is nonessential |

Keep icon artwork smaller than its interactive target. Use shared default control height for adjacent fields and buttons to align baselines.
