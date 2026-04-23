# Deuda Cero Legal — Design System

Brand design system for **Deuda Cero Legal**, a Spanish legal-financial firm specializing in the **Ley de Segunda Oportunidad** (Second Chance Law) — helping individuals legally cancel debt.

The firm's differentiator is a **contable-financiero** (accounting-financial) approach: technical precision in front of the judge to maximize exoneration success rates. Positioning is **luxury + trust** — Oxford Blue, gold accents, and a coral CTA, aimed at Spanish-speaking users who mostly arrive from mobile ads.

---

## Index

| File / folder | Purpose |
|---|---|
| `README.md` | This file. Context, voice, visual foundations, iconography. |
| `colors_and_type.css` | All design tokens as CSS variables (color, type, spacing, radii, shadows, motion). |
| `assets/` | Logos (4 variants), cover art, horizontal + vertical social posts. |
| `preview/` | Design-system preview cards shown in the Design System tab. |
| `ui_kits/landing/` | Full landing-page recreation per the brief — header, hero, pain section, differentiator, 5-step Viability Test, authority list, FAQ, footer + floating WhatsApp. |
| `SKILL.md` | Agent-skill manifest — makes this folder invocable as a Claude Code / Claude Skill. |

---

## Sources

- **Codebase / Figma:** none attached. The firm does not have an existing site code — this system is built from the brand brief + the marketing assets below.
- **Visual assets (attached via Import):** `DEUDA CERO LEGAL/` containing:
  - `LOGO/` — 4 logo variants (shield lettermark, with/without wordmark).
  - `Portadas/portada.png` — cover banner, used as hero reference.
  - `Posts/Horizontal/` — 1 split-panel editorial post.
  - `Posts/Vertilcal/` — 5 vertical (story-format) social posts.
- **Brief:** provided by the user — defines page structure, copy, palette intent, and CRO goals.

### Palette reconciliation (important)

The user brief lists a four-color palette:
- Oxford Blue `#1B263B` ✅ matches assets
- "Dorado Ámbar" `#E0E1DD` ⚠️ — this hex is **Platinum (light gray)**, not amber gold. The assets themselves use a real warm gold (~`#E0B458` / `#C8962B`) for headlines like "¿AHOGADO EN DEUDAS?". The system keeps **both** (gold as the accent, platinum as a neutral) and flags this to the user.
- Pure White `#FFFFFF` ✅
- Coral CTA `#F28482` ✅

The logo also contains an **emerald green** (~`#1E6B47`) that the brief does not mention. It's strong visual equity and is preserved as a supporting brand color (success states, checkmarks, secondary accents).

---

## Content Fundamentals — Voice & Tone

**Language:** Peninsular Spanish (Spain). Never translate.

**Stance:** Empathetic authority. The audience is financially stressed — copy must feel like a calm, expert hand on the shoulder. Never preachy, never hard-sell, never condescending. Gravitas over hype.

**Person:** Use **tú**, never *usted*. "Te ayudamos", "Recupera tu tranquilidad", "Tus deudas". It's warm but not casual.

**Casing:**
- Headlines in **sentence case** with a leading **¿Question?** pattern is very on-brand: *"¿Ahogado en deudas?"*, *"¿Detén las llamadas de recobro?"*, *"¿El sobreendeudamiento te quita el sueño?"*
- Social posts use **ALL-CAPS on the primary hook** for punch: `¿AHOGADO EN DEUDAS?`, `RECUPERA TU TRANQUILIDAD`.
- Body copy is sentence case.
- CTAs are short, imperative verbs: "Empezar Test", "Envíanos un mensaje", "Comenzar ahora".

**Length & rhythm:** Short lines. Three-word hooks. The pattern is *Pain → Promise → Proof → Path*. Example from `portada.png`:
> ¿AHOGADO EN DEUDAS? / Te ayudamos a empezar de cero / Estudio gratuito y sin compromiso / [checklist of 4 outcomes] / CTA

**Key vocabulary (use these words):**
- Tranquilidad, Libertad, Empezar de cero, Segunda Oportunidad
- Exoneración, Cancelación, Viabilidad
- Acoso telefónico, Embargos, Morosidad, ASNEF, Badexcug, Hacienda, Seg. Social
- Despacho, Jurídico, Contable-financiero, Juez

**Reassurance phrases (use on CTAs / near forms):**
- "Análisis 100% gratuito y sin compromiso"
- "Confidencialidad garantizada"
- "Primera consulta gratuita"

**Forbidden:**
- No emojis (except the WhatsApp glyph on the floating CTA).
- No exclamation stacks, no "¡¡¡!", no "AMAZING", no hype.
- No English mixed in unless it's a legal term (ASNEF stays ASNEF).
- No pity tropes. Dignity first.
- No irony or humor — this is debt, not entertainment.

**Example before/after:**
- ❌ "¡Di adiós a tus deudas para siempre! 🚀"
- ✅ "Cancelamos tus deudas legalmente. Recupera tu tranquilidad hoy mismo."

---

## Visual Foundations

### Color

**Primary surfaces are two-state:** either pure white (trust, clarity, legal-document feel) or deep Oxford Blue (authority, premium). Very little in between — the brand avoids mid-gray backgrounds. Navy goes almost-black (`--dcl-navy-950`) in social posts to push depth.

**Gold is used sparingly as an eyebrow / accent / underline**, never as a background. It never touches body copy — only headlines, highlighted keywords, and iconographic details.

**Emerald green** appears only in the logo and in success/confirmation contexts (checkmarks, "Deuda cancelada", "Libertad" calendar mark in the cover art).

**Coral** is reserved — it only appears on the primary CTA button. Do not use it for anything else. This scarcity is what makes the CTA pop.

### Typography

- **Display:** Montserrat (700–900) — tight tracking, big confident headlines. Uppercase for short hooks.
- **Body:** Inter (400–600) — legible, neutral.
- **Mono:** system mono, used only for legal-document cues (case numbers, references).
- Prefer `text-wrap: balance` on headlines and `text-wrap: pretty` on body copy.
- Type scale is mobile-first with `clamp()` — never assume desktop.

### Spacing & layout

- 4px baseline; sections breathe with **64–128px vertical rhythm** on desktop, **40–64px on mobile**.
- Max content width 1200px.
- Generous gutters (24px min). White space is a feature, not a bug.
- **Single focal point per screen.** Never compete two CTAs.

### Backgrounds

- **No gradients on primary surfaces** — flat navy or flat white.
- The one gradient allowed is a subtle vertical darken (`--dcl-navy-900` → `--dcl-navy-950`) behind hero/post art, giving photographs depth.
- No hand-drawn illustrations, no repeating patterns, no mesh gradients. Legal brand — minimalist always.
- Full-bleed **photographic imagery** appears in social posts but is used cropped + darkened behind text.

### Corner radii

- Cards: `--r-lg` (16px) to `--r-xl` (24px).
- Buttons: pill (`--r-pill`) for CTAs — matches the "Envíanos un mensaje" button in the cover.
- Inputs: `--r-md` (10px).

### Shadows & elevation

- **Soft, low, cool-shadowed.** Shadows use the navy ink color at low alpha — never pure black.
- Three-step elevation: `--shadow-sm`, `--shadow-md`, `--shadow-lg`.
- The CTA gets a **coral glow** (`--shadow-cta`) to cue affordance.
- No inner shadows. No neumorphism.

### Borders

- On light: 1px `--border-subtle` (`#D9DDE3`).
- On dark: 1px `--border-on-dark` (`#2F4768`).
- Focus rings: 3px gold at ~18% alpha (`--shadow-gold-glow`).

### Motion

- **Restrained.** 140–240ms with `ease-out`. No bounces, no springs, no parallax.
- Hover: subtle translate-y (-2px) + shadow bump. On CTA, the coral gets 6% brighter.
- Press: 0.97 scale + shadow reduction.
- Accordion/quiz step transitions: 240ms opacity + height.

### Imagery vibe

- Photography is **warm-lit, shallow-depth**. Always shows real people (couples, individuals) at the moment of *relief*, not stress — smiling, calm, in bright interiors. Stress imagery (hands clasped, bill piles) lives only in *before* contexts.
- B&W is not used. Cool-tones only on dark-themed posts.

### Transparency & blur

- Glassmorphism is not used. Surfaces are opaque.
- Overlays on photos use solid navy at 70–85% alpha, not blur.

### Layout rules (fixed)

- Header: 72–80px tall, white on light mode, fully opaque (no transparency tricks).
- Floating WhatsApp CTA: bottom-right, 56–64px circle, coral fill with WhatsApp glyph, always above everything.
- Never more than one sticky element at a time.

---

## Iconography

**System:** [Lucide](https://lucide.dev) via CDN (`lucide-static` SVG or `lucide-react`). The brief calls for it by name and the stroke style matches the brand's clean, legal-document aesthetic.

- Stroke width: **1.75** (default). Never fill Lucide icons.
- Default color: `--dcl-navy-900` on light, `--dcl-white` on dark.
- Accent color: `--dcl-gold-500` for icons beside headlines ("prestige" badges).
- Success color: `--dcl-emerald-500` for checkmark chips (used heavily in the cover — *"Sin más llamadas"*, *"Registro eliminado"*).
- CTA color: `--dcl-coral-500` for WhatsApp / action-forward glyphs.

**Specific icons used by section:**
- Header: `Scale` (justice) beside the logo wordmark, `Menu` for mobile nav.
- Pain cards: `PhoneOff` (acoso telefónico), `ShieldAlert` (embargos), `FileX` (morosidad/ASNEF).
- Authority list: `ShieldCheck` (seguridad), `Clock` (rapidez), `Lock` (confidencialidad).
- Quiz: `Check`, `ArrowRight`, `ArrowLeft`, `MessageCircle` (WhatsApp).
- FAQ: `ChevronDown` (collapsed) / `ChevronUp` (expanded).
- Trust strip: `BadgeCheck`, `Gavel`, `FileText`.

**Logo uses:**
- `assets/logo-primary.png` — shield lettermark only, for header/favicon.
- `assets/logo-alt.png` — lockup with wordmark + tagline "Soluciones legales para tu segunda oportunidad", for footers/press.
- `assets/logo-white-bg.png` — clean version for printing.

**Emoji:** never, except the WhatsApp glyph built into the floating CTA is acceptable (it's a recognized brand).

**Unicode chars:** the inverted Spanish opening punctuation (`¿`, `¡`) is a *signature* — never replace it with just `?`/`!`.

**Flag:** Lucide is a **substitution** — the brief calls for it by name but no existing icon set came with the assets. If the firm later adopts a custom icon set, swap at the token layer.

---

## Product surfaces

There is **one product**: the landing page (conversion-focused, mobile-first, Spanish market, ad traffic). No app, no admin, no docs site. The UI kit at `ui_kits/landing/` is the full recreation.

---

## Open questions / caveats

- **Palette brief error:** `#E0E1DD` labeled as "Dorado Ámbar" is actually platinum gray. We use true gold (`#E0B458`) in the system, per the real assets. Confirm with brand owner.
- **No webfont files** were provided. Montserrat + Inter are loaded via Google Fonts. If brand owns licensed files, drop them into `fonts/` and swap `@import`.
- **No icon files** provided. Using Lucide as a close match to the brief.
- **No long-form legal copy** (privacy notice, aviso legal) — placeholder in footer.
