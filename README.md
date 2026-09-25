# Trans Cidadania — Design System

**Trans Cidadania** is a support, information, and welcoming platform for **transgender people in Brazil**. It gathers trustworthy, plain-language information about accessing public-health (SUS) services, legal rights, and local support — in one safe, accessible place. The product is a single-page React website (no backend) covering five areas:

1. **Home** — hero, four entry cards, floating assistant.
2. **Processo Transexualizador** — how the SUS gender-affirming process works (5-step roadmap).
3. **Hormonioterapia** — accessing hormone therapy through SUS.
4. **Retificação de Nome e Gênero** — legal name/gender change (ADI 4275, Provimento CNJ 73/2018).
5. **Locais de Apoio e Denúncia** — health services, NGOs, and reporting channels.

A UI-only **chatbot** ("Assistente Trans Cidadania") is a floating button + modal with a fixed "in development" reply — no AI, no API.

The visual identity is built on the **Transgender Pride flag** (pink `#F5A9B8`, light blue `#5BCEFA`, white) set against **elegant dark navy** surfaces (`#1a1a2e`, `#16213e`), with **glassmorphism cards**, soft flag-tinted gradients, and gentle microinteractions. The tone is warm, dignified, and protective.

---

## Sources provided

There was **no codebase or Figma file** — the system is built from the written brand brief plus supplied reference material:

- **`uploads/Screenshot_7.png`** — reference for the 5-step "winding road" roadmap (numbered colored map-pins). Recreated as the `RoadmapProcesso` component.
- Content PDFs (informational source material, not design):
  - `uploads/Itinerários de acesso.pdf`
  - `uploads/guia_retificacao_genero.pdf`
  - `uploads/cartilha-alterac3a7c3a3o-nome-e-genero.pdf`
  - `uploads/OrientacoesparaRetificacao página 2.pdf`
  - `uploads/Direito e identidade de gênero.pdf`
  - `uploads/PERGUNTAS MAIS FREQUENTES (FAQ) estado.pdf`

> Because no production code was supplied, the design foundations below are the **canonical source of truth** for this brand. If an official logo, brand guide, or real product code exists, attach it and we'll reconcile.

---

## CONTENT FUNDAMENTALS

**Language:** Brazilian Portuguese, throughout.

**Voice & address:** Second person, **"você"** — direct, warm, reassuring. The reader is addressed as a person seeki1g help, never as a "case." Institutional facts are stated plainly and accurately (laws, portarias, ages, deadlines) but always framed around *what the reader can do*.

**Tone:** Welcoming, dignified, protective, factual. It balances **emotional warmth** ("feito com amor para a comunidade trans brasileira") with **rigorous accuracy** (cites Portarias nº 1.707/457/2.803, ADI 4275, Resolução CFM 2.265/2019, Provimento CNJ 73/2018). Never clinical-cold, never saccharine.

**Casing:** Sentence case for body and most headings; Title Case for proper nouns and section names ("Processo Transexualizador", "Retificação de Nome e Gênero"). Acronyms uppercase (SUS, UBS, ESF, TFD, HCPA, ANTRA, CNJ, STF).

**Examples (verbatim brand copy):**

- Tagline: *"Apoio, informação, acolhimento e cuidado para pessoas trans."*
- Welcome: *"Na Trans Cidadania, você encontra informações confiáveis, esclarece dúvidas e localiza ONGs e serviços próximos a você. Tudo em um só lugar, de forma segura e acolhedora."*
- Card CTA: *"Saiba mais"* · Hero CTAs: *"Explorar"*, *"Falar com nosso assistente"*
- Footer: *"Trans Cidadania — feito com amor para a comunidade trans brasileira."*

**Emoji:** Essentially none in the brand surface. The only sanctioned emoji is the **🔧** in the chatbot's "in development" reply, and ✅/❌ used as semantic markers in "what can/can't be changed" lists. Treat emoji as functional markers, not decoration.

**Microcopy rules:** Action labels are short verbs/verb-phrases ("Explorar", "Saiba mais", "Voltar para o início"). Alerts (e.g. "E se o cartório se recusar?") use a distinct warning color and a calm, solution-first structure (what to do → who to contact). Always give a next step and a contact channel.

---

## VISUAL FOUNDATIONS

**Color vibe.** Trans-flag pink + light-blue are the *emotional* colors; they appear as gradients, glows, and accents — rarely as large flat fills. Large surfaces are **dark navy** (`#1a1a2e` → `#14132a`), which makes the pastel flag colors glow. Two extra accents extend the palette: **lilac** `#C77DFF` (Retificação) and **mint** `#00C9A7` (Locais). Each of the four home cards owns one accent; that color carries through to its page.

**Backgrounds.** No photography in chrome. The hero uses a **layered radial-gradient wash** — a blue glow top-left, a pink glow top-right, over a navy vertical gradient (`--grad-hero`) — evoking flag colors as soft light, not stripes. Subtle animated "wave/particle" motion is optional and very low-amplitude. Inner sections are solid navy or faint glass panels. Avoid heavy full-saturation gradient blocks.

**Glassmorphism.** The signature surface. Cards are `rgba(255,255,255,0.06)` fills with `backdrop-filter: blur(18px)`, a `1px` hairline border `rgba(255,255,255,0.14)`, and a soft drop shadow. On hover they lift (`translateY(-6px)`) and gain a colored **glow ring** in their accent color (`--glow-blue/pink/lilac/mint`).

**Type.** **Poppins** for display/headings (geometric, friendly, 600–800 weights, tight `-0.02em` tracking on large sizes). **Inter** for body and UI (16px base, 1.6 line-height). Hero headline often uses a **flag gradient text clip** (`--grad-flag-vivid`). Overlines are uppercase Inter 12px with `0.14em` tracking.

**Spacing & layout.** 4px base scale. Generous vertical rhythm (`64–96px` section padding). Content max-width \~1120px, centered. Home cards in a responsive 2×2 grid (1 column on mobile), `24px` gap. Mobile-first.

**Corner radii.** Friendly and rounded: cards `--r-lg (22px)`, buttons/pills `--r-pill`, inputs `--r-md (16px)`, small chips `--r-sm`. Nothing sharp-cornered.

**Borders.** Almost always hairline translucent white (`--glass-border`) on dark, or a 1–2px accent-colored border on hover/active. Accent left-border-only cards are **avoided** — borders are full and even.

**Shadows / elevation.** Two systems: (1) neutral depth — `--shadow-sm/md/lg` (soft, dark, large-blur, no harsh edges); (2) **accent glows** for focus/hover (`--glow-*`), which double as the focus-visible ring. Cards float; the page feels layered over a dark base.

**Animation.** Gentle and reassuring — never bouncy/playful-jarring. Standard transition `200–300ms` with `cubic-bezier(0.22,1,0.36,1)` (soft ease-out). Hover = lift + glow + slight brightness. Press = scale to `0.97`. Entrances fade-up `16px`. Background gradients may drift slowly (8–14s) at low amplitude. Respect `prefers-reduced-motion`.

**Hover / press states.** Hover: brighten fill, raise elevation, reveal accent glow ring, optional icon nudge. Press/active: `transform: scale(0.97)` + slightly darker fill. Links: lighten to `--link` + underline. Focus-visible: 2px accent ring (`--glow-*`).

**Transparency & blur.** Used deliberately — glass cards, the sticky header (blurred navy `rgba(20,19,42,0.7)`), the chatbot modal backdrop. Not everywhere; solid navy panels anchor dense content.

**Iconography color.** Icons are line-style, often inheriting their section accent (blue/pink/lilac/mint) or `--fg-2` for neutral UI. The roadmap pins are solid-filled accent map-pins with white numerals.

**Cards summary.** Rounded (`22px`), translucent glass on dark, hairline border, soft shadow at rest → accent glow + lift on hover. A leading icon chip (rounded square, accent-tinted) sits top-left; title in Poppins; 2-line Inter description; "Saiba mais" link/button.

---

## ICONOGRAPHY

The brand uses **[Lucide](https://lucide.dev)** line icons (the icon set named in the brief, `lucide-react`). Lucide is a clean, consistent **stroke-based** set (2px stroke, rounded caps) that pairs well with Poppins/Inter. Loaded from CDN (`lucide@latest`) — see `assets/lucide-icon.js` helper and the UI kit.

**Section icons (semantic mapping):**

- Processo Transexualizador → `heart-pulse` (blue)
- Hormonioterapia → `pill` / `flask-conical` (pink)
- Retificação de Nome → `file-text` / `pen` (lilac)
- Locais de Apoio → `map-pin` / `shield` (mint)
- Brand mark → `heart-handshake` (hands + heart) in flag gradient
- Chatbot → `message-circle` / `sparkles`
- Reporting → `shield`, `phone`; Checks → `check`, `x`

**Emoji:** Not used decoratively. Sanctioned functional uses only: 🔧 (chatbot "in development"), ✅/❌ (allowed/not-allowed lists). Prefer Lucide `check`/`x` where layout allows.

**Logo:** No official logo was supplied. The wordmark "Trans Cidadania" pairs Poppins 700 with the `heart-handshake` glyph in a flag-gradient chip — composed in the `BrandMark` component (`ui_kits/website/Header.jsx`) and previewed in `preview/brand-logo.html`. This is a composed **placeholder**, not an official asset — please provide the real logo if one exists.

> **Substitution flag:** Lucide is the brief's specified set, so it's an exact match, not a substitution. Fonts (Poppins/Inter) are the specified brand fonts, loaded via Google Fonts CDN — also exact, not a substitution.

---

## Design system components (bundle)

The compiler exposes **11 components** on `window.TransCidadaniaDesignSystem_0e97ae` — consume them in `@dsCard` HTML via:

```js
const { Header, Hero, Footer, Chatbot, Button, SectionCard } = window.TransCidadaniaDesignSystem_0e97ae;
```

Each component has a sibling `.d.ts` with full prop types. The bundle is loaded via `<script src="../../_ds_bundle.js">` (relative from `ui_kits/website/`).

Exposed components: `Animations`, `App`, `Cards`, `Chatbot`, `Footer`, `Header`, `Hero`, `HomeSections`, `Pages`, `Primitives`, `Roadmap`.

---

## Index / manifest

**Root**

- `README.md` — this file (context, content, visual foundations, iconography, manifest).
- `colors_and_type.css` — all color, type, spacing, radius, shadow tokens (CSS vars).
- `SKILL.md` — Agent Skill front-matter so this folder works in Claude Code.

**`assets/`** — `lucide-icon.js` (Lucide CDN icon helper + React `Icon` wrapper). No official logo was supplied; the wordmark is composed at runtime by the `BrandMark` component in the UI kit (flag-gradient chip + `heart-handshake` glyph).

**`preview/`** — design-system cards rendered in the Design System tab (colors, type, spacing, components, brand). One small HTML file per concept.

**`ui_kits/website/`** — high-fidelity recreation of the Trans Cidadania site.

- `index.html` — interactive click-through (Home → section pages → chatbot modal).
- `*.jsx` — Header, Hero, SectionCard, RoadmapProcesso, InfoSection, ContactCard, AlertCard, Chatbot, Footer, Button, Badge.
- `README.md` — kit-specific notes.

There are **no slide templates** for this brand, so `slides/` is intentionally omitted.
