# CLAUDE.md — JioSignage Design System

Source: Jio Design System (JDS) — Core JioComponents Figma file, "Action - Button" component set.
Official docs (login required): https://ds.jio.com/components/action-button/#design

This file is Claude's source of truth for UI work on JioSignage. Use ONLY the values below —
no arbitrary hex codes, spacing, or radii. Extend this file as more components are pulled from Figma.

---

## Foundations

### Colors (Primary scale)
| Token | Hex | Usage |
|---|---|---|
| `primary/30` | `#9999FF` | Hover background (Primary button) |
| `primary/50` | `#3535F3` | Primary/Default base background |
| `primary/60` | `#000093` | Pressed background · Secondary/Tertiary text · Focus ring |
| `primary/70` | `#00004C` | Text on hover state |
| `primary/inverse` | `#FFFFFF` | Text/icon on filled (dark) buttons |
| `primary/background` | `#FFFFFF` | Contrast appearance background |
| `primary/grey-60` | `#B5B5B5` | Secondary button border |
| `primary/grey-100` | `#141414` | Text on Contrast appearance |

### Feedback colors
| Token | Hex | Usage |
|---|---|---|
| `global/feedback-success-50` | `#25AB21` | Positive appearance background |
| `global/feedback-error-50` | `#FA2F40` | Negative appearance background |

### Typography
Font family: **JioType**, weight **Bold (700)** for button labels.

| Size token | Font size | Line height | Letter spacing |
|---|---|---|---|
| Small | 16px | 24px | -0.08px |
| Medium | 16px | 24px | -0.08px |
| Large | 18px | 24px | -0.09px |
| Extra large | 24px | 32px | -0.12px |

### Shape
- Border radius: **250px** (fully rounded / pill) on all button sizes.
- Focus ring: 4px solid border, `primary/60`.

### Spacing (per size)
| Size | Padding (H / V) | Icon size | Gap (icon–label) |
|---|---|---|---|
| Small | 12px / 4px | 16px | 4px |
| Medium | 16px / 8px | 24px | 8px |
| Large | 24px / 12px | 24px | 8px |
| Extra large | 32px / 16px | 32px | 8px |

---

## Component: Button (Action - Button)

Props: `appearance` (Default / Positive / Negative / Contrast) × `kind` (Primary / Secondary / Tertiary) ×
`size` (Small / Medium / Large / Extra large) × `state` (Normal / Hover / Pressed / Focused / Disabled / Loading) ×
`variant` (Label only / Icon only / Label + Icon)

### Kind = Primary (filled)
| Appearance | Background | Text/Icon color |
|---|---|---|
| Default | `primary/50` `#3535F3` | `primary/inverse` white |
| Positive | `#25AB21` | white |
| Negative | `#FA2F40` | white |
| Contrast | `primary/background` white | `primary/grey-100` `#141414` |

### Kind = Secondary (outlined)
- Background: transparent
- Border: 1px solid `primary/grey-60` `#B5B5B5`
- Text: `primary/60` `#000093`

### Kind = Tertiary (text/link style)
- Background: none, no border, no horizontal padding
- Text: `primary/60` `#000093`

### States (shown for Default/Primary; same pattern applies across appearances)
| State | Background | Text | Notes |
|---|---|---|---|
| Normal | `primary/50` `#3535F3` | white | — |
| Hover | `primary/30` `#9999FF` | `primary/70` `#00004C` | background lightens, text darkens |
| Pressed | `primary/60` `#000093` | white | background darkens |
| Focused | `primary/50` `#3535F3` | white | + 4px solid `primary/60` ring |
| Disabled | `primary/50` `#3535F3` | white | 30% opacity on whole button |
| Loading | `primary/50` `#3535F3` at 30% opacity | — | centered spinner icon replaces label; see [Loader Spinner](https://ds.jio.com/components/loader-spinner/) |

---

## Rules for Claude
- Use only the tokens above. Do not invent hex values, font sizes, or radii.
- Always use pill-shaped buttons (`border-radius: 250px`) — never square or slightly-rounded corners.
- Primary kind = filled background; Secondary = outlined; Tertiary = text-only. Don't mix these treatments.
- Maintain icon-to-label gap and padding exactly per size table above.
- WCAG AA minimum contrast on all text/background pairs.
- This file currently documents the **Button** component only. Other components (inputs, cards, nav, etc.)
  should be pulled from the same Figma library and appended here in the same format before use.

## Open items / to extend later
- Icon-only and Label+Icon variants use the same color/state tokens as Label-only (dimensions differ per size table).
- Loading-state spinner asset/animation spec: see JDS Loader Spinner docs.
- Typography, color, and spacing tokens for other components (forms, cards, navigation) not yet captured — pull from Figma the same way (see button nodes above) when building those screens.
