# DESIGN.md — Thirteen4Six Visual Language

## Brand Identity
The command center uses the **Thirteen4Six** brand identity — the same look and feel as the in-unit printed materials (Keurig guide, WIFI card, Welcome doc, Washer-Dryer guide). This creates a cohesive experience across the physical space and the digital tools. The brand is warm, approachable, slightly playful, and confident.

## Brand Mark
- **Name:** Thirteen4Six (stylized as "Thirteen" + "4Six" stacked)
- **Wordmark style:** Decorative blackletter/gothic serif
- **Color:** Deep blue on light backgrounds, white on deep blue backgrounds
- **Usage:** Footer of every page, login screen

## Colors

### Primary Palette
| Token | Hex | Usage |
|-------|-----|-------|
| --brand-blue | #0A3191 | Primary text, headings, icons, buttons, brand color |
| --brand-blue-dark | #071E5E | Hover states, footer background |
| --brand-blue-light | #1A4FBF | Links, interactive highlights |
| --cream | #FAF6ED | Page background (warm, inviting) |
| --cream-dark | #F0E8D8 | Card hover, subtle section backgrounds |
| --white | #FFFFFF | Card backgrounds, input fields |

### Status Colors (for dashboard metrics)
| Token | Hex | Usage |
|-------|-----|-------|
| --success | #1B7A3D | On-track, positive delta, completed items |
| --success-bg | #E8F5ED | Success card background tint |
| --warning | #C87D14 | Approaching target, needs attention |
| --warning-bg | #FFF6E5 | Warning card background tint |
| --danger | #B82525 | Off-track, critical, missed targets |
| --danger-bg | #FDF0F0 | Danger card background tint |

### Neutral Palette
| Token | Hex | Usage |
|-------|-----|-------|
| --text | #0A3191 | Primary text (brand blue — NOT black) |
| --text-secondary | #4A5A7A | Secondary text, labels, metadata |
| --text-muted | #8A92A6 | Placeholders, disabled text |
| --border | #D4CBB8 | Card borders, dividers (warm tint) |
| --border-light | #E8E0D0 | Subtle borders |

## Typography

### Headlines (display)
- **Style:** Bold, condensed, uppercase, decorative slab-serif
- **CSS:** `font-family: 'Playfair Display', 'Georgia', serif; font-weight: 900; text-transform: uppercase; letter-spacing: 0.02em;`
- **Fallback note:** The printed materials use a custom condensed decorative face. Playfair Display Black is the closest web-safe match for the bold, characterful feel.
- **Color:** Always var(--brand-blue)

### Body Text
- **Style:** Clean sans-serif, comfortable reading
- **CSS:** `font-family: 'DM Sans', 'Inter', -apple-system, system-ui, sans-serif; font-weight: 400;`
- **Color:** var(--brand-blue) for primary, var(--text-secondary) for secondary

### Brand Mark / Logo Text
- **Style:** Blackletter/gothic decorative
- **CSS:** `font-family: 'UnifrakturMaguntia', 'Playfair Display', serif;` (or render as SVG)
- **Note:** For the web, consider embedding the wordmark as an SVG for exact reproduction

### Type Scale
| Token | Size | Weight | Usage |
|-------|------|--------|-------|
| --text-xs | 11px | 500 | Badges, tiny labels |
| --text-sm | 13px | 400 | Metadata, captions |
| --text-base | 15px | 400 | Body text |
| --text-md | 17px | 500 | Card titles, emphasis |
| --text-lg | 22px | 700 | Section headings |
| --text-xl | 28px | 900 | Page titles |
| --text-hero | 44px | 900 | Hero metrics (revenue, ADR) |

### Line Height
- Headlines: 1.1
- Body: 1.5
- Hero numbers: 1.0

## Spacing
- **Base unit:** 4px
- **Scale:** 4, 8, 12, 16, 20, 24, 32, 40, 48, 64

## Component Patterns

### "HOW TO" Badge (from printed materials)
```
[ HOW TO ]
Background: var(--brand-blue)
Text: white, 11px, 600 weight, uppercase, letter-spacing 0.08em
Border-radius: 6px
Padding: 4px 12px
```
Adapted for dashboard as section label badges:
```
[ REVENUE ]  [ PRICING ]  [ ACTIONS ]  [ MARKET ]
```

### Step Marker / Number Circle (from printed materials)
```
( 1 )
Shape: circle, 32px diameter
Fill: var(--brand-blue)
Text: white, 16px, 700 weight, centered
```
Adapted for dashboard as metric indicators, list markers, completion badges.

### Score Card
```
┌─────────────────────────┐
│ [ REVENUE ]             │  ← badge label (brand blue bg, white text)
│                         │
│ $1,856                  │  ← value (44px, 900 weight, brand blue)
│ March 2026              │  ← subtitle (13px, text-secondary)
│                         │
│ ● Target: $3,800        │  ← delta (13px, status color)
└─────────────────────────┘
Background: var(--white)
Border: 1px solid var(--border)
Border-radius: 12px
Border-left: 4px solid (status color)
Padding: 24px
```

### Card
```
┌─────────────────────────┐
│ [ SECTION ]  Card Title │  ← badge + title (17px, 500 weight)
│─────────────────────────│
│                         │
│  [card content]         │  ← body (15px, 400 weight)
│                         │
└─────────────────────────┘
Background: var(--white)
Border: 1px solid var(--border)
Border-radius: 12px
Padding: 24px
Hover: border-color var(--brand-blue-light), subtle shadow
```

### Alert / Important Notice (from printed materials)
```
⚠ Important: Alert message text here
Border: 1.5px solid var(--brand-blue)
Border-radius: 10px
Background: var(--cream)
Padding: 16px 20px
Icon: warning triangle in brand blue
Text: 15px, brand blue
```

### Button
```
[ Action Label ]
Primary: bg var(--brand-blue), text white, border-radius 8px
Hover: bg var(--brand-blue-dark)
Secondary: bg transparent, border 1.5px solid var(--brand-blue), text var(--brand-blue)
Hover: bg var(--cream-dark)
Padding: 10px 20px
Font: 14px, 600 weight
```

### Footer (from printed materials)
```
┌─────────────────────────────────────────┐
│                          Thirteen4Six   │
└─────────────────────────────────────────┘
Background: var(--brand-blue-dark)
Text: white, brand wordmark, right-aligned
Height: 48px
```

## Chart Colors
- Primary series: var(--brand-blue) #0A3191
- Secondary series: var(--brand-blue-light) #1A4FBF
- Target line: dashed, var(--warning) #C87D14
- Positive delta: var(--success) #1B7A3D
- Grid lines: var(--border-light) #E8E0D0
- Chart background: var(--white)
- Tooltip: var(--brand-blue-dark) background, white text

## Illustrations & Icons
- **Style:** Simple, outlined, monochrome blue — matching the playful cartoon style from printed materials
- **Color:** var(--brand-blue) only — never multicolor
- **Line weight:** Bold outlines (2px stroke)
- **Personality:** Friendly, slightly retro, approachable
- **For dashboard:** Use simple SVG icons in brand blue. Avoid generic icon libraries — keep the hand-drawn feel where possible.

## Layout
- **Page background:** var(--cream) #FAF6ED
- **Max content width:** 1200px, centered
- **Grid:** CSS Grid, 2-column for main layout (60/40 split)
- **Responsive:** Single column below 768px

## Responsive Breakpoints
- **Desktop:** > 1024px — full grid layout
- **Tablet:** 768–1024px — condensed grid, smaller cards
- **Mobile:** < 768px — single column stack

## Accessibility
- Minimum font size: 12px (13px preferred for body)
- All brand blue text on cream background passes WCAG AA (contrast ratio ~8:1)
- All white text on brand blue background passes WCAG AAA
- Focus-visible: 2px solid var(--brand-blue), 2px offset
- No information conveyed by color alone — always pair with text or icon
- Interactive targets: minimum 44px touch area

## Password Gate Screen
The login screen should match the Welcome Doc aesthetic:
- Centered Thirteen4Six wordmark (large, brand blue)
- Simple password input field
- "Enter" button in brand blue
- Cream background
- Footer bar with brand mark
- No mention of financial data or Airbnb — just the brand name
