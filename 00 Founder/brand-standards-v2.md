# Brand Standards
**Version 2.0 | March 2026**

---

## COLOR PALETTE

### Primary
| Name | Hex | Usage |
|------|-----|-------|
| Teal | `#13B5A2` | Primary accent, CTAs, highlights, links |
| Navy | `#132539` | Headings, dark sections, authority |

### Secondary
| Name | Hex | Usage |
|------|-----|-------|
| Teal Light | `#DCFAF5` | Light backgrounds, badges |
| Teal Dark | `#12917E` | Hover states, gradient stops |
| Navy Light | `#2A3F54` | Secondary dark, gradient stops |
| Cream | `#F9F8F5` | Warm background surfaces |
| Gold | `#D4A338` | Premium accents, highlights (sparingly) |

### Neutrals
| Role | HSL | Usage |
|------|-----|-------|
| Background | `210 20% 98%` | Page background |
| Foreground | `215 40% 12%` | Primary body text |
| Muted | `210 15% 92%` | Subtle backgrounds |
| Muted Foreground | `215 15% 45%` | Secondary text, captions |
| Border | `210 20% 88%` | Dividers, input borders |

### Gradients
| Name | Definition | Usage |
|------|-----------|-------|
| Hero | `135deg, hsl(210 20% 98%) → hsl(168 60% 92%)` | Hero backgrounds |
| Accent | `135deg, hsl(168 84% 45%) → hsl(168 80% 35%)` | CTA buttons |
| Dark | `135deg, hsl(215 50% 15%) → hsl(215 35% 25%)` | Dark sections |

### Rules
- Teal `#13B5A2` is the primary accent — never substitute other greens or blues
- Backgrounds are Cream or page background — never dark mode for documents
- No red, orange, or yellow as accents
- Text on teal buttons is always white

---

## TYPOGRAPHY

### Fonts
| Role | Font | Weights | Usage |
|------|------|---------|-------|
| Display | **Sora** | 300–800 | Headings, hero text |
| Body | **Inter** | 300–700 | Body copy, UI, navigation, buttons |
| Documents/fallback | **Arial** | — | When Sora/Inter unavailable |

### Scale
| Element | Font | Weight | Notes |
|---------|------|--------|-------|
| H1 | Sora | Bold (700) | Hero headlines only. One per page. |
| H2 | Sora | Bold (700) | Section headings |
| H3 | Sora | Bold (700) | Subsection headings |
| Body | Inter | Regular (400) | Primary reading text |
| Caption | Inter | Regular (400) | Secondary/muted text |
| Nav | Inter | Semibold (600) | Navigation links |
| Button | Inter | Semibold (600) | All button labels |

### Rules
- Headings: sentence case only — never ALL CAPS for headings
- Labels and section markers: ALL CAPS with letter spacing
- Headings use tight tracking
- Body uses antialiased rendering
- Max two font weights in a single layout

---

## BUTTONS & CTAs

| Variant | Background | Text | Usage |
|---------|-----------|------|-------|
| Hero | Teal | White | Primary CTAs |
| Hero Outline | Transparent + navy border | Navy | Secondary hero CTAs |
| Accent | Teal | White | In-section CTAs |
| Navy | Navy | White | Dark section CTAs |
| Outline | Transparent + border | Foreground | Secondary actions |

### Rules
- Low friction — preserve autonomy
- Match readiness level — never push before trust is built
- No urgency theater
- One primary CTA per page/section

---

## DOCUMENT & ARTIFACT STANDARDS

### Documents (Word, PDF)
- Page size: US Letter (8.5" × 11")
- Margins: 1 inch all sides
- Font: Arial (Inter if web-rendered)
- Accent: `#13B5A2` for headers, highlights
- Background: White or `#F9F8F5`
- Table borders: `hsl(210 20% 88%)`

### HTML / Web Artifacts
- Display font: Sora (Google Fonts)
- Body font: Inter (Google Fonts)
- Accent: `#13B5A2`
- Background: `#F9F8F5` or `hsl(210 20% 98%)`
- Text: `hsl(215 40% 12%)`
- Secondary text: `hsl(215 15% 45%)`
- Buttons: Teal background, white text, rounded-lg
- Cards: White background, border, rounded-lg, shadow-sm
- Max container: 1400px, centered

### Section hierarchy
1. Label (ALL CAPS, muted foreground, small)
2. Heading (Sora bold, navy, large)
3. Body (Inter regular, foreground)
4. Supporting detail (Inter, muted foreground, smaller)

---

## QUICK REFERENCE

```
Teal:            #13B5A2
Teal Dark:       #12917E
Teal Light:      #DCFAF5
Navy:            #132539
Navy Light:      #2A3F54
Cream:           #F9F8F5
Gold:            #D4A338

Display font:    Sora
Body font:       Inter
Doc fallback:    Arial
```
