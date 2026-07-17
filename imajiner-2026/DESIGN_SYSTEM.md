# Imajiner 2026 — Design System

Derived from `outputs/index.html` and `outputs/css/home.css`. Dark, atmospheric agency aesthetic: deep night backgrounds, cool teal accents, light display type, full-bleed photography, and restrained motion.

---

## Foundations

### Color palette

| Token | Value | Role |
| --- | --- | --- |
| `night` | `#071012` | Page / hero base |
| `night-elevated` | `#091416` | Section mid-tone (help gradient) |
| `ink` | `#ecf7f5` | Primary text |
| `ink-soft` | `#e9f4f3` / `#eef7f5` | Headings |
| `muted` | `rgba(226, 239, 237, 0.66)` | Hero supporting copy |
| `muted-deep` | `rgba(224, 239, 236, 0.58)` | Body / lead copy |
| `teal` | `#87cbd0` | Accent (eyebrow, underlines) |
| `teal-mid` | `#93d4d7` | Section eyebrow / status dot |
| `teal-soft` | `#afd9d9` / `#b8dddc` | Secondary headline lines, emphasis |
| `teal-deep` | `#5da7ad` | Gradient end / deeper accent |
| `line` | `rgba(232, 244, 242, 0.22)` | Hairline dividers (hero) |
| `line-soft` | `rgba(218, 239, 236, 0.14)` | Section rules / meta borders |
| `warm` | `#efb86d` | Rare highlight (visual trace only) |

**Semantic roles**

- **Background**: `night`, with subtle teal radial washes and a faint grid on content sections.
- **Text primary**: `ink` / `ink-soft`.
- **Text secondary**: `muted` / `muted-deep`.
- **Accent**: `teal` family — never purple; warm gold is decorative only.
- **Interactive fill**: teal gradient (`#96d8db` → `#65abb1`); hover lightens to `#ace5e6` → `#78bbc0`.
- **Inverse on CTA hover**: text becomes `night` on `ink` fill (nav CTA).

### Typography

| Role | Family | Weight | Size | Tracking | Line height |
| --- | --- | --- | --- | --- | --- |
| Display / H1 | Manrope | 300 | `clamp(55px, 6.05vw, 104px)` | `-0.065em` | `0.93` |
| Section H2 | Manrope | 300 | `clamp(58px, 7.8vw, 132px)` | `-0.068em` | `0.92` |
| Story H3 | Manrope | 300 | `clamp(43px, 4.65vw, 76px)` | `-0.055em` | `1.01` |
| Hero eyebrow | Manrope | 500 | `clamp(11px, 0.82vw, 14px)` | `0.46em` | — |
| Section eyebrow / kicker | DM Sans | 500 | `11px` | `0.36em` | — |
| Body | DM Sans | 300 | `clamp(16px, 1.18–1.3vw, 19–22px)` | `-0.025em` (hero) | `1.55–1.72` |
| Nav / UI | DM Sans | 400–500 | `15–16px` | `-0.015em` | — |
| Meta chips | DM Sans | 500 | `10px` | `0.14em` | — |
| Visual label | DM Sans | 400 | `9px` | `0.2em` | — |
| Story number | Manrope | 400 | `13px` | `0.18em` | — |

**Rules**

- Headlines are light (`300`), tight, and often multi-line with a softer teal secondary line or `<em>` emphasis (`font-style: normal`, color `teal-soft`).
- Eyebrows are uppercase with wide tracking.
- Body copy stays light weight; avoid bold for long paragraphs.
- Fallbacks: `"DM Sans", Arial, sans-serif` and `"Manrope", sans-serif`.

### Spacing scale

Prefer fluid clamps over a rigid rem ladder. Recurring values:

| Token-ish | Value | Use |
| --- | --- | --- |
| `space-xs` | `8–14px` | Icon gaps, meta chip padding |
| `space-sm` | `22–36px` | Proof item padding, small stacks |
| `space-md` | `34–58px` | CTA gaps, story meta top |
| `space-lg` | `80–150px` | Section intro padding |
| `space-xl` | `90–210px` | Story / intro vertical rhythm |

### Container & grid

- **Shell**: `width: min(100% - clamp(40px, 9vw, 152px), 1510px)`; centered.
- **Mobile shell** (≤760px): `min(100% - 38px, 680px)`.
- **Hero copy**: `min(47vw, 660px)` desktop; full width on mobile.
- **Help intro**: 2-col `1.4fr / 0.55fr`, gap `clamp(40px, 8vw, 145px)`.
- **Story**: 2-col copy/media `0.72fr / 1.28fr` (reverse flips order); gap `clamp(45px, 7vw, 120px)`.

### Radius, borders, shadows

| Element | Radius | Border | Shadow |
| --- | --- | --- | --- |
| Primary button / pills | `999px` / `99px` | — / `1px solid line-soft` (meta) | `0 12px 32px rgba(70, 150, 158, 0.2)` |
| Nav CTA | `99px` | `1px solid rgba(236, 247, 245, 0.63)` | — |
| Nav toggle | `50%` | `1px solid line` | — |
| Mobile menu | `20px` | `1px solid rgba(236, 247, 245, 0.13)` | `0 20px 60px rgba(0, 0, 0, 0.4)` |
| Visual frame | `clamp(20px, 2.2vw, 34px)` | inset `1px solid rgba(196, 231, 229, 0.14)` | `0 38px 90px rgba(0, 0, 0, 0.38)` |

Hairlines are preferred over heavy borders. Corner brackets (34×34px L-shapes) mark visual frames.

### Icons & imagery

- **Icons**: stroke SVG, ~22–25px, `stroke-width ≈ 1.35`, color near `ink` at ~80% opacity.
- **Logo**: white wordmark; width `clamp(112px, 9.6vw, 150px)` (116px mobile).
- **Hero**: full-bleed photographic background, slight scale (`1.025`), left-weighted dark shade for copy, soft grain overlay (`opacity 0.12`, `mix-blend-mode: soft-light`).
- **Story visuals**: 4:3 (1:1 on small screens), object-cover with parallax, wash gradient, optional animated trace/scan, uppercase micro-label with teal pulse dot.

### Breakpoints

| Width | Behavior |
| --- | --- |
| `≤1080px` | Tighter nav; hide last two links; slightly smaller H1 |
| `≤980px` | Help intro & stories stack to one column |
| `≤760px` | Hamburger nav; hero shade becomes vertical; proof becomes 3-col grid |
| `≤600px` | Tighter help padding; square visuals |
| `≤430px` | CTAs stack; smaller proof type; hero image crops higher |

### Motion

- **Easing**: `cubic-bezier(0.16, 1, 0.3, 1)` (`--ease`).
- **Page load**: staggered reveals (`reveal-down`, `reveal-up`, `reveal-line`, `scene-in`) ~0.9–1.8s.
- **Hover**: 0.3–0.45s; lift `-2px` / `-3px` on CTAs; underline grows; arrow nudges `5px`.
- **Scroll**: story copy/media fade-up on intersect; image parallax (`--parallax`, capped ±38px).
- **Ambient**: infinite trace / scan / pulse on visuals only.
- **Reduced motion**: collapse durations; disable parallax.

---

## Components

### Brand

- White logo image, left-aligned in nav.
- Linked to home; `aria-label` includes brand name.

### Navigation

| Part | Default | Hover / open |
| --- | --- | --- |
| Link | `rgba(244, 249, 248, 0.88)`, 15px | White; teal underline expands left→right |
| Dropdown chevron | 11px SVG | `translateY(2px)` |
| CTA (outline) | Pill, translucent border | Fill `ink`, text `night`, lift `-2px` |
| Toggle | Hidden ≥760px; 43px circle | Expands to X via span transforms |
| Mobile panel | Closed: opacity 0 | Open: blurred night panel, stacked links |

Focus: inherit browser outline unless a custom focus ring is added later. Disabled/loading: not present yet.

### Buttons

**Primary (`.button--primary`)**

- Min height 56px (50px mobile), min width 180px (146px mobile).
- Teal gradient fill, dark text `#061113`, medium weight 500.
- Hover: lighter gradient, stronger shadow, lift `-3px`.

**Text (`.button--text`)**

- No fill/radius; arrow icon 25px.
- Hover: full-width underline draws leftward; arrow `translateX(5px)`.

### Eyebrow

- Uppercase label above headlines.
- Hero: Manrope, teal, wider tracking (`0.46em`).
- Sections: DM Sans, `#93d4d7`, tracking `0.36em`.

### Proof row

- Three icon + label items separated by vertical hairlines.
- Desktop: horizontal row under hero (left ~52% / 680px).
- Mobile: equal 3-column grid, stacked icon-over-label, centered.

### Meta chips (`.story__meta span`)

- Pill outline, uppercase micro labels.
- Default only (no selected state in current page). Color ~54% ink.

### Visual frame (`.visual`)

- Rounded media container with wash, corner marks, optional label.
- States: idle ambient motion; parallax while in view; reduced-motion freezes parallax.

---

## Layout & page patterns

### Hero (full-bleed)

First viewport = one composition:

1. Nav (logo · links · konsultasi)
2. Brand-forward display headline (3 lines)
3. One short supporting sentence
4. Primary + text CTA
5. Edge-to-edge studio photo + shade + grain
6. Optional proof strip at bottom (secondary to the composition)

Do not add cards, floating badges, or inset media in the hero.

### Help / capability intro

- Tall intro block: large H2 (“Imajiner membantu Anda”) + lead with top hairline.
- Soft radial teal wash + masked grid texture on `night` gradient.

### Story / narrative split

- Alternating copy | media (`.story--reverse` flips).
- Number + rule, kicker, title with teal emphasis, body, meta chips.
- Ghost oversized number in background at ~2.5% opacity.

### Page types (current / recommended)

| Type | Status |
| --- | --- |
| Marketing home (hero + narrative) | Implemented |
| Portfolio listing / detail | Extend with same night/teal system, Manrope titles, hairline sections |
| Contact / WhatsApp CTA | Reuse primary button + outline nav CTA |
| Empty / error | Recommendation: same night base, light Manrope title, one primary CTA |

---

## Responsive behavior

- **Desktop (>1080)**: Wide shell, full nav, left-weighted hero copy over photo, horizontal proof.
- **Tablet (760–1080)**: Drop trailing nav items; slightly narrower copy; keep hero structure.
- **Mobile (≤760)**: Hamburger; hero content bottoms out over a stronger vertical shade; proof grids; CTAs may stack ≤430px.
- **Help/stories (≤980)**: Single column; media follows copy; reverse order resets so media always follows on small screens.
- **Touch targets**: Primary buttons stay ≥50px tall; toggle 43×43px.

---

## CSS variables (canonical)

```css
:root {
  --ink: #ecf7f5;
  --muted: rgba(226, 239, 237, 0.66);
  --teal: #87cbd0;
  --teal-deep: #5da7ad;
  --night: #071012;
  --line: rgba(232, 244, 242, 0.22);
  --ease: cubic-bezier(0.16, 1, 0.3, 1);
}
```

Prefer extending these tokens over introducing new hue families.
