---
name: google-design-mastery
version: 1.0.0
status: derived-reference
scope: web-ui
intent: >-
  Create modern web interfaces that feel unmistakably Google-inspired:
  intelligent, approachable, spacious, precise, useful, lively and quietly playful.
  This skill combines public Google Design / Material guidance with visual observations
  from the supplied Google Antigravity screen recording. It is not an official Google
  specification and must not imply affiliation with Google.
---

# Google Design Mastery — `skill.md`

## 0. Core directive

When this skill is active, do not treat “Google style” as a collection of colors, rounded buttons, or a Google logo. Treat it as a **behavioral design system**.

The objective is to produce an interface where:

- information is easy to understand before it is beautiful;
- visual hierarchy is obvious without being aggressive;
- interaction is expressive but never noisy;
- motion explains what changed, where it came from, and what the user can do next;
- typography carries much of the brand personality;
- icons behave like language, not decoration;
- whitespace creates confidence;
- color is used as semantic punctuation rather than wallpaper;
- large visual moments are balanced by extremely simple controls;
- delight appears as small discoveries, not constant spectacle;
- accessibility, responsiveness and performance are part of the design, not cleanup work.

Google’s public design platform describes Material as its open-source UI system and emphasizes that design spans style, branding, interaction and motion. Google Design’s own identity work also describes simplicity, intelligence, accessibility/usefulness, dynamic motion and consistency as central concerns. The recording supplied with this task shows a contemporary Google/Antigravity-style marketing site that applies a lighter, more editorial interpretation of these ideas rather than a literal Material component library.

**Important distinction:** Material 3 is the formal Google design system. The uploaded Antigravity site is a **specific visual direction** built with Google-adjacent cues: Google Sans-like typography, extreme whitespace, thin outlines, pill controls, large editorial headlines, expressive media, multi-color particles and restrained black/white UI. Do not pretend every visual observation below is an official Material rule.

---

# 1. Design north star

## 1.1 The desired emotional arc

A Google-inspired interface should generally create this sequence:

**Calm → clarity → curiosity → confidence → delight → momentum.**

The user should not feel:

**confusion → visual pressure → UI friction → “what am I supposed to click?”**

Think in emotional temperature:

| Layer | Desired feeling | Design mechanism |
|---|---|---|
| First impression | Calm confidence | clean canvas, generous whitespace, strong typographic hierarchy |
| Orientation | Intelligence | predictable navigation, meaningful grouping, concise labels |
| Discovery | Curiosity | small motion cues, expressive imagery, scroll reveals |
| Interaction | Responsiveness | fast state changes, subtle hover/press behavior |
| Completion | Satisfaction | clear feedback, smooth transitions, meaningful success states |
| Return visits | Familiarity | consistent spacing, icon grammar, recurring motion language |

The key is **restraint**. A delightful element only feels delightful because most of the interface is quiet.

## 1.2 “Googley” means useful + alive

Do not copy surface aesthetics blindly. Instead ask on every component:

1. What is the user trying to understand?
2. What is the least visual noise that communicates it?
3. What interaction state needs to be visible?
4. Can motion make the relationship clearer?
5. Can the same idea be communicated with less UI?
6. Does the element feel approachable rather than intimidating?
7. Does it remain understandable with animation disabled?

---

# 2. Visual language

## 2.1 The base canvas

Default light mode should feel like **an extremely clean sheet with almost no visual texture**, except where texture is intentionally introduced as atmosphere.

Recommended base values for a Google/Antigravity-inspired marketing site:

```css
:root {
  --bg: #ffffff;
  --fg: #202124;
  --fg-strong: #0b0c0e;
  --fg-muted: #5f6368;
  --fg-subtle: #80868b;
  --surface: #f8f9fa;
  --surface-2: #f1f3f4;
  --border: #dadce0;
  --border-subtle: #e8eaed;

  --google-blue: #4285f4;
  --google-red: #ea4335;
  --google-yellow: #fbbc04;
  --google-green: #34a853;

  --shadow-1: 0 1px 2px rgb(60 64 67 / 10%);
  --shadow-2: 0 4px 12px rgb(60 64 67 / 12%);
  --shadow-3: 0 12px 32px rgb(60 64 67 / 16%);

  --radius-sm: 10px;
  --radius-md: 16px;
  --radius-lg: 24px;
  --radius-pill: 999px;
}
```

These values are a **web implementation starting point**, not a claim that every Google property uses exactly these tokens.

Google brand references historically use blue, red, yellow and green, while contemporary Material themes structure color into semantic roles such as primary/on-primary/container, secondary, tertiary, error, background and surface. Use the relationship between tones and semantic roles rather than randomly placing brand colors everywhere.

## 2.2 Color philosophy

Use the color hierarchy in this order:

1. neutral canvas;
2. dark primary text;
3. muted text;
4. subtle borders;
5. one interaction/accent color;
6. multi-color Google accents only for expressive moments.

### Neutral usage

- **White:** main canvas and negative space.
- **Near-black:** hero headlines, important controls, high-emphasis UI.
- **Gray:** secondary descriptions and metadata.
- **Very light gray:** card backgrounds, low-emphasis surfaces.
- **Border gray:** separation without boxes.

### Google colors

Use the four canonical Google colors as **signals**, not a repeating rainbow theme.

Appropriate:

- animated dots/particles;
- tiny status indicators;
- a multicolor logo mark;
- a decorative highlight;
- a focused AI/assistant moment;
- a transition where the four colors merge or travel.

Avoid:

- four-color gradients behind every section;
- coloring every button;
- rainbow text for ordinary copy;
- using color where typography or spacing already communicates the hierarchy.

### Dark mode

Do not merely invert white and black. Rebuild the tonal hierarchy:

```css
[data-theme="dark"] {
  --bg: #0b0c0e;
  --fg: #f8f9fa;
  --fg-muted: #bdc1c6;
  --surface: #17191c;
  --surface-2: #202124;
  --border: #3c4043;
}
```

On dark surfaces, reduce visual glare and use accent color selectively. Material 3’s color-role model is especially useful here because it makes foreground/background relationships explicit.

---

# 3. Typography — the strongest brand signal

## 3.1 Font choice

For a current Google-inspired build, prefer **Google Sans Flex** where licensing and product requirements allow it. Google has published Google Sans and Google Sans Flex openly; Google describes Google Sans Flex as a variable family with axes for weight, width, slant, optical size, grade and roundness.

For body copy and fallback text, use a highly legible sans-serif stack:

```css
font-family:
  "Google Sans Flex",
  "Google Sans",
  Roboto,
  Arial,
  sans-serif;
```

For multilingual products, select a language-appropriate fallback. Never allow the headline font to become the only source of legibility.

## 3.2 Typography personality

The observed Antigravity site uses an unusually large, light-feeling geometric headline. The effect comes from:

- large size;
- low-to-medium weight;
- generous line height;
- wide visual spacing around the text;
- short, readable line groups;
- high contrast against a clean background.

The headline should feel **confident without shouting**.

### Suggested web scale

```css
:root {
  --text-display: clamp(3.4rem, 7vw, 7.5rem);
  --text-h1: clamp(2.75rem, 5.5vw, 5.75rem);
  --text-h2: clamp(2.2rem, 4vw, 4rem);
  --text-h3: clamp(1.65rem, 2.7vw, 2.75rem);
  --text-body-lg: 1.25rem;
  --text-body: 1rem;
  --text-small: 0.875rem;
  --text-label: 0.875rem;
}
```

Use `clamp()` so typography scales continuously instead of snapping between arbitrary breakpoints.

## 3.3 Display headline rules

A hero headline should:

- usually be 1–3 lines;
- have a deliberate maximum width;
- not run edge-to-edge unless the art direction demands it;
- use a line height around 0.95–1.05 for large display type;
- avoid excessive font weight;
- contain one clear message, not a paragraph;
- visually dominate navigation and body copy.

Example:

```css
.hero-title {
  max-width: 1100px;
  margin-inline: auto;
  font-size: var(--text-display);
  font-weight: 450;
  line-height: 0.98;
  letter-spacing: -0.045em;
  text-wrap: balance;
}
```

Do not use negative tracking blindly. Test actual glyph shapes and optical size; variable fonts can change the ideal spacing.

## 3.4 Body copy

Body text should feel quieter but never faint.

Recommended:

```css
.body-copy {
  font-size: 1rem;
  line-height: 1.55;
  color: var(--fg-muted);
  max-width: 62ch;
}
```

Use readable line lengths. For dense technical copy, do not imitate the enormous marketing headline scale.

## 3.5 Labels and metadata

Metadata in the recording is compact, neutral and low drama. Use:

- 12–14px;
- medium weight;
- muted color;
- consistent baseline alignment;
- short labels such as date/category/status.

Do not turn metadata into mini-headlines.

---

# 4. Layout system

## 4.1 Whitespace is a component

Whitespace is not “empty.” It is the mechanism that tells the eye what belongs together.

Use **large negative space around ideas** and **tight spacing inside ideas**.

A useful mental model:

```text
SECTION GAP:        very large
GROUP GAP:          medium
ELEMENT GAP:        small
INLINE GAP:         tiny
```

If two elements should feel related, move them closer. If they are conceptually separate, increase the gap before drawing another divider.

## 4.2 Container

Recommended starting point:

```css
.container {
  width: min(100% - 48px, 1400px);
  margin-inline: auto;
}
```

At smaller widths:

```css
@media (max-width: 720px) {
  .container {
    width: min(100% - 32px, 1400px);
  }
}
```

For editorial sections, allow a narrower internal text column while keeping media wider.

## 4.3 Grid

Use a responsive grid rather than manually positioned blocks.

```css
.grid-12 {
  display: grid;
  grid-template-columns: repeat(12, minmax(0, 1fr));
  gap: clamp(16px, 2vw, 32px);
}
```

Common patterns:

- 8/4 for heading + supporting explanation;
- 6/6 for paired product stories;
- 4/4/4 for three compact benefits;
- full-width media with a narrow copy overlay;
- horizontally overflowing card rails on desktop.

## 4.4 Section rhythm

Marketing pages should breathe. A useful starting rhythm:

```css
section {
  padding-block: clamp(96px, 12vw, 220px);
}
```

Hero sections can be taller; utility sections can be shorter.

Never force every section to exactly the same height. Repetition should come from a rhythm, not a template prison.

---

# 5. Navigation

## 5.1 Header personality

The supplied recording shows a very simple header:

- compact brand lockup at left;
- a small number of primary navigation items;
- minimal dropdown indicators;
- a dark pill CTA at right;
- strong horizontal whitespace;
- no heavy navigation container in the content itself.

The header should appear **quiet and inevitable**.

## 5.2 Header behavior

At initial load:

- opacity 1;
- no dramatic bounce;
- logo and nav aligned on a single visual baseline;
- CTA immediately understandable.

On scroll:

Option A — keep it static for maximum editorial calm.

Option B — introduce a compact “floating” header only after a meaningful threshold such as 48–120px of scroll.

Do not make the header constantly change shape every time the scroll direction flips.

## 5.3 Dropdowns

A dropdown should:

1. open after deliberate intent;
2. anchor to the trigger;
3. use a clear surface and subtle shadow/border;
4. respect pointer velocity;
5. close on Escape;
6. keep keyboard focus logical;
7. avoid theatrical animation.

Recommended motion:

```css
.dropdown {
  opacity: 0;
  transform: translateY(-4px) scale(0.98);
  transform-origin: top center;
  transition:
    opacity 160ms ease,
    transform 180ms cubic-bezier(.2,.8,.2,1);
}

.dropdown[data-open="true"] {
  opacity: 1;
  transform: translateY(0) scale(1);
}
```

---

# 6. Buttons

## 6.1 Button personality

The observed Antigravity design uses strong black pills for primary actions and extremely quiet outlined/light pills for secondary actions.

That creates a powerful binary:

**“do the thing” = dark**

**“explore / learn” = light**

Use that contrast intentionally.

## 6.2 Primary CTA

Recommended starting point:

```css
.btn-primary {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  min-height: 48px;
  padding-inline: 22px;
  border-radius: 999px;
  background: #111214;
  color: #fff;
  font-size: 16px;
  font-weight: 520;
  border: 1px solid transparent;
  transition:
    transform 180ms cubic-bezier(.2,.8,.2,1),
    box-shadow 180ms ease,
    background-color 160ms ease;
}
```

Hover:

- move upward by ~1px;
- slightly increase shadow or luminosity;
- icon can translate 1–2px;
- never inflate by 10%.

Press:

- scale to ~0.97–0.985;
- shorten the transition;
- return quickly.

Example:

```css
.btn-primary:hover {
  transform: translateY(-1px);
}

.btn-primary:active {
  transform: translateY(0) scale(0.985);
  transition-duration: 70ms;
}
```

## 6.3 Secondary CTA

Secondary buttons should feel like **an open door**, not a weaker error-prone control.

```css
.btn-secondary {
  background: #f8f9fa;
  color: #202124;
  border: 1px solid #e1e3e6;
  box-shadow: none;
}
```

Hover:

- background becomes slightly darker;
- border gains contrast;
- optional subtle lift.

## 6.4 Icon buttons

Icon-only controls require stronger interaction states because they lack labels.

Recommended hit area:

```css
.icon-btn {
  inline-size: 44px;
  block-size: 44px;
  border-radius: 50%;
}
```

The visual glyph can be 20–24px while the interactive target stays larger.

---

# 7. Icons

## 7.1 Use a coherent icon family

Do not mix random SVG packs.

Google’s Material Symbols provide a coherent family with multiple styles and adjustable axes including weight, fill, grade and optical size. Choose a single family for a product surface unless the visual identity explicitly requires otherwise.

Recommended default for a calm modern interface:

- Material Symbols Outlined for utility UI;
- Rounded when the brand is intentionally softer;
- Sharp only when the product needs a more technical/dense character.

## 7.2 Icon sizing

Starting scale:

| Context | Symbol size |
|---|---:|
| Dense metadata | 16–18px |
| Standard UI | 20–24px |
| Button leading icon | 18–20px |
| Navigation | 20–24px |
| Feature icon | 28–36px |
| Hero decoration | custom |

## 7.3 Icon optical tuning

Material Symbols can vary `wght`, `FILL`, `GRAD` and `opsz`.

Use the **fill axis for state**, not for random animation.

Example:

```css
.material-symbols {
  font-variation-settings:
    'FILL' 0,
    'wght' 420,
    'GRAD' 0,
    'opsz' 24;
  transition: font-variation-settings 180ms ease;
}

[aria-pressed="true"] .material-symbols {
  font-variation-settings:
    'FILL' 1,
    'wght' 420,
    'GRAD' 0,
    'opsz' 24;
}
```

The official Material Symbols documentation describes fill as useful for state transitions and weight/grade as visual-thickness controls.

## 7.4 Never use icon decoration without purpose

Do not add sparkles because “Google uses sparkles.”

A sparkle should communicate something like:

- generation;
- intelligence;
- enhancement;
- discovery;
- magical transformation.

A folder icon should communicate a folder. The visual system should remain semantically honest.

---

# 8. Borders, surfaces and cards

## 8.1 Prefer composition over boxes

A Google-inspired page often feels expensive because it does **not** put a border around every concept.

Use:

- spacing;
- typography;
- alignment;
- media;
- subtle rules;

before adding another card.

## 8.2 When a card is appropriate

Cards are useful for:

- previewable content;
- product alternatives;
- blog items;
- tools with independent actions;
- media tiles;
- information that can be mentally separated from the surrounding content.

The recording’s “Latest Blogs” section is a strong example: large media tiles, rounded image corners, then title, metadata and a small text link.

## 8.3 Card anatomy

```text
┌──────────────────────────────┐
│                              │
│           MEDIA              │
│                              │
├──────────────────────────────┤
│ Headline                     │
│ Date   Category              │
│ Read blog  →                 │
└──────────────────────────────┘
```

Do not put six badges, a giant shadow and three nested containers inside a simple blog card.

## 8.4 Border radius

Use a small set of radii, not one unique radius per element.

Suggested:

```css
--radius-sm: 10px;
--radius-md: 16px;
--radius-lg: 24px;
--radius-xl: 32px;
--radius-pill: 999px;
```

Pill controls should remain clearly pill-shaped. Media cards can use 20–32px depending on scale.

---

# 9. Shadows and elevation

Google’s Material heritage uses shadow/light as an affordance, but the contemporary editorial direction seen in the recording uses very restrained depth.

Therefore:

- use shadows sparingly;
- prefer a subtle border on large white surfaces;
- avoid huge diffuse shadows around everything;
- reserve stronger elevation for overlays, menus and floating UI.

Recommended light shadow:

```css
box-shadow: 0 4px 18px rgb(60 64 67 / 10%);
```

Do not create a “dribbble card ocean” where every section floats above the page.

---

# 10. Motion design — the hidden half of the system

## 10.1 Motion has jobs

Every animation should answer at least one of these:

- **Where did this come from?**
- **What changed?**
- **What is interactive?**
- **What is currently active?**
- **Where should I look next?**
- **Did the system receive my action?**

If it answers none, remove it.

Material’s current motion guidance emphasizes motion as a system for expressing spatial/temporal relationships and maintaining a coherent interaction model. In a marketing site, apply that principle with restraint.

## 10.2 Motion hierarchy

### Micro motion: 80–220ms

Use for:

- hover;
- focus;
- icon changes;
- button press;
- small opacity shifts.

### Component motion: 180–400ms

Use for:

- popovers;
- menus;
- accordions;
- media expansion;
- card transitions.

### Section motion: 350–900ms

Use for:

- hero entrance;
- large editorial transitions;
- image reveals;
- staged scroll sequences.

### Ambient motion: continuous

Use only when:

- it creates atmosphere;
- the movement remains subtle;
- it does not compete with reading;
- CPU/GPU cost is controlled;
- reduced-motion mode is respected.

## 10.3 Easing

Use simple easing families.

```css
:root {
  --ease-standard: cubic-bezier(.2, .8, .2, 1);
  --ease-enter: cubic-bezier(.16, 1, .3, 1);
  --ease-exit: cubic-bezier(.7, 0, .84, 0);
}
```

Do not overuse `cubic-bezier()` as decoration. The exact numbers are starting points, not sacred Google constants.

## 10.4 Enter animations

Prefer:

- opacity 0 → 1;
- translateY 8–24px → 0;
- scale 0.98 → 1;
- clip/reveal for editorial media.

Avoid:

- bouncing every heading;
- spinning icons into view;
- 3D flips for ordinary content;
- long 1.5–3 second entrances for routine components.

## 10.5 Staggering

Staggering is useful for creating the feeling of coordinated intelligence.

Use small intervals:

```js
const delay = index * 45;
```

Typical range:

- 24ms: nearly simultaneous;
- 40–60ms: elegant cascade;
- 80–120ms: strongly staged;
- >150ms: likely to feel slow for ordinary lists.

Stagger only a small logical group, not an entire page of 30 elements.

---

# 11. Cursor design

## 11.1 Default cursor rule

Do not replace the OS cursor by default. A conventional cursor is familiar and accessible.

Custom cursor behavior should be an enhancement layered around the native pointer, especially on desktop.

## 11.2 Magnetic button effect

The pointer can create a subtle magnetic attraction toward a large CTA.

Desired sensation:

**“The interface notices me.”**

Not:

**“The website is dragging my mouse.”**

Implementation concept:

```js
const max = 8;
const strength = 0.18;

function updateMagnet(el, pointerX, pointerY) {
  const rect = el.getBoundingClientRect();
  const cx = rect.left + rect.width / 2;
  const cy = rect.top + rect.height / 2;
  const dx = pointerX - cx;
  const dy = pointerY - cy;

  const x = Math.max(-max, Math.min(max, dx * strength));
  const y = Math.max(-max, Math.min(max, dy * strength));

  el.style.transform = `translate3d(${x}px, ${y}px, 0)`;
}
```

Rules:

- only on large clickable elements;
- max displacement ~4–10px;
- return with a spring-like but controlled transition;
- disable on coarse pointers/touch;
- do not transform layout-reflowing containers.

## 11.3 Cursor spotlight

A local spotlight can reveal ambient color without changing the entire page.

```css
.page {
  --cursor-x: 50vw;
  --cursor-y: 50vh;
  background:
    radial-gradient(
      420px circle at var(--cursor-x) var(--cursor-y),
      rgb(66 133 244 / 6%),
      transparent 70%
    ),
    var(--bg);
}
```

Do not leave the spotlight intense enough to look like a gaming UI.

## 11.4 Cursor trail / particles

The supplied Antigravity recording shows a very light particle/dash field surrounding the hero. That effect can be made pointer-responsive.

Rules for a Google-like implementation:

- tiny strokes/dots;
- low opacity;
- sparse enough to preserve reading;
- randomized but deterministic where possible;
- gentle directional bias around pointer or scroll;
- no giant glowing comet tail.

A strong implementation uses a `<canvas>` or GPU-friendly element layer rather than hundreds of independently animated DOM nodes.

## 11.5 Cursor proximity reactions

The most sophisticated version is **proximity-aware content**.

Examples:

- tiny particles rotate slightly toward the pointer;
- a hero icon follows the pointer by 2–4px;
- a CTA underline expands when the pointer enters a wider invisible interaction region;
- a decorative star changes orientation when the pointer passes nearby.

Never make decorative motion stronger than the actual control response.

## 11.6 Mobile behavior

On mobile there is no cursor. Replace cursor behaviors with:

- scroll-driven ambient motion;
- tap states;
- press feedback;
- touch-friendly ripple or highlight where appropriate;
- static or reduced particle motion.

---

# 12. Scroll behavior

## 12.1 Scroll should reveal, not fight

A good scroll experience has three layers:

1. regular document flow;
2. occasional reveal animations;
3. selected cinematic moments.

Do not turn the entire page into a WebGL obstacle course.

## 12.2 Reveal pattern

Use IntersectionObserver or a framework equivalent.

Recommended:

```css
.reveal {
  opacity: 0;
  transform: translateY(18px);
  transition:
    opacity 600ms cubic-bezier(.16,1,.3,1),
    transform 700ms cubic-bezier(.16,1,.3,1);
}

.reveal.is-visible {
  opacity: 1;
  transform: none;
}
```

## 12.3 Scroll-linked movement

Use scroll-linked motion for:

- background particles;
- large media crops;
- subtle image parallax;
- typography that shifts slightly into place;
- progress cues.

Avoid strong parallax on text because it can reduce readability and increase motion discomfort.

## 12.4 Pinned stories

A pinned storytelling section can create a premium, product-launch feel:

```text
[PINNED VISUAL]      [STEP 01]
                     explain

[PINNED VISUAL]      [STEP 02]
                     explain

[PINNED VISUAL]      [STEP 03]
                     explain
```

The visual changes while the surrounding copy advances. Use this sparingly.

---

# 13. Hero composition

## 13.1 Hero anatomy based on the supplied recording

The observed opening page contains:

1. compact brand lockup;
2. simple nav;
3. dark primary download CTA;
4. a small brand/agent mark;
5. huge centered headline;
6. two contrasting CTA buttons;
7. a field of tiny multicolor marks surrounding the hero;
8. lots of white negative space.

This creates a useful formula:

**minimal UI frame + oversized message + tiny energetic detail.**

That contrast is important.

## 13.2 Hero spacing

The hero should often have more vertical breathing room than the content below it.

Suggested structure:

```html
<section class="hero">
  <div class="hero-ambient" aria-hidden="true"></div>

  <div class="hero-mark">...</div>

  <h1>...</h1>

  <p class="hero-support">...</p>

  <div class="hero-actions">
    <a class="btn-primary">...</a>
    <a class="btn-secondary">...</a>
  </div>
</section>
```

## 13.3 Multicolor particle field

This is not “just confetti.” It gives the hero energy and can communicate AI, motion, intelligence, and Google-like playfulness without altering the neutral interface.

Use:

- blue as the most common cool accent;
- red/yellow/green as sparse accents;
- tiny elongated dashes rather than large circles;
- different lengths and orientations;
- slight radial or directional flow;
- very low opacity around the headline itself, higher density toward the perimeter.

Never allow particles to cross letters densely enough to reduce contrast.

---

# 14. “Feeling engineering” — making effects trigger emotion

## 14.1 The effect must have a psychological purpose

Map visual effects to intended feelings:

| Effect | Emotion |
|---|---|
| Soft fade-up | calm arrival |
| 1–2px button lift | confidence |
| Quick press compression | physicality |
| Tiny icon fill transition | completion |
| Magnetic CTA | attention / agency |
| Slow ambient particles | wonder |
| Multicolor accent burst | delight |
| Large clean type | authority |
| Generous whitespace | trust |
| Smooth image reveal | anticipation |
| Precise hover highlight | craftsmanship |

## 14.2 The “80/20 delight” rule

Approximately 80% of the interface should remain calm and predictable; roughly 20% may provide expressive moments.

This is not a measured Google ratio. It is a design heuristic that prevents novelty fatigue.

## 14.3 Surprise must be local

A delightful effect should happen near the user’s action.

Bad:

> Hover a button → 3 unrelated sections start moving.

Good:

> Hover a button → button rises 1px, icon shifts slightly, edge highlight appears.

## 14.4 Motion should have a “quiet reset”

After an interaction completes, the interface should settle back into calm. Avoid leaving every card glowing, rotating or pulsing forever.

---

# 15. Media design

The recording uses media as large rounded visual statements, especially for developer personas, SDK previews and blog cards.

## 15.1 Image rules

Prefer imagery that is:

- high-resolution;
- editorial rather than generic stock;
- compositionally simple;
- compatible with the surrounding typography;
- cropped intentionally.

A photograph should have a role. Do not insert an image just to fill an empty rectangle.

## 15.2 Video rules

Video should feel like part of the interface, not an embedded TV player.

### Autoplay background/video

Use for:

- atmosphere;
- product visualization;
- short silent demonstrations;
- hero motion.

Requirements:

```html
<video
  autoplay
  muted
  playsinline
  loop
  preload="metadata"
>
</video>
```

Provide:

- a poster frame;
- a meaningful reduced-data strategy;
- controls when the video is content rather than decoration;
- reduced-motion alternatives where appropriate.

## 15.3 Video interaction

For a media card:

Idle:

- poster image;
- soft play symbol.

Hover:

- play symbol grows by a tiny amount;
- image crop can shift 1–2%;
- optional dark scrim appears lightly.

Click:

- player expands or navigates to the full story;
- transition should preserve spatial context when possible.

## 15.4 Avoid video UI clutter

Do not expose a full media-control chrome when the role is a decorative hero loop.

Conversely, do not hide controls from an informational video users are expected to watch.

---

# 16. Blog / content rails

The recording shows a horizontally flowing “Latest Blogs” region.

## 16.1 Card rail rules

Desktop:

- 3–5 cards partially visible depending on viewport;
- consistent card widths;
- strong image ratio;
- thin separators if needed;
- no excessive card shadow.

Mobile:

- horizontal snap scrolling or a clean stacked list;
- card width around 82–90vw if horizontal;
- keep the next card partially visible only when it helps communicate scrollability.

## 16.2 Metadata

Use a predictable order:

```text
TITLE
Date   Category
Read blog →
```

The metadata must never visually overpower the title.

---

# 17. Decorative systems

## 17.1 Dots, dashes and particles

Use one geometry family. Do not mix:

- circles;
- stars;
- diamonds;
- noise blobs;
- 3D crystals;

unless the art direction explicitly uses multiple families.

The recording leans heavily toward tiny dashes/points as ambient decoration.

## 17.2 Animated decorative lines

Thin lines can communicate data, systems, or flow.

Best uses:

- connecting related concepts;
- progress;
- reveal masks;
- section separators;
- subtle network/agent visuals.

Avoid turning the site into a sci-fi HUD. Google-inspired design is generally clearer and more human than cyberpunk.

## 17.3 Gradients

Use gradients for atmosphere, not basic layout.

Good:

```css
background:
  radial-gradient(circle at 30% 20%, rgb(66 133 244 / 14%), transparent 34%),
  radial-gradient(circle at 70% 60%, rgb(52 168 83 / 9%), transparent 38%),
  #fff;
```

Bad:

```css
background: linear-gradient(135deg, blue, purple, pink, yellow);
```

unless the product’s concept truly calls for it.

---

# 18. Interaction states

Every interactive element should have a complete state model.

Required conceptual states:

```text
idle
hover
focus-visible
active/pressed
disabled
loading
success
error
selected (when applicable)
```

Never design only the idle state.

## 18.1 Focus

Keyboard focus should be visible and elegant.

Example:

```css
:focus-visible {
  outline: 3px solid rgb(66 133 244 / 50%);
  outline-offset: 3px;
}
```

Do not remove outlines without replacing them with an equally strong focus indicator.

## 18.2 Loading

Use local feedback.

Good:

- button label becomes “Downloading…”;
- icon changes to progress;
- nearby progress indicator appears.

Bad:

- freeze the entire page;
- show a giant loading screen for a tiny action.

---

# 19. Accessibility

Google-quality design is incomplete if it only looks good on a screenshot.

## Minimum rules

- keyboard navigation must work;
- focus must be visible;
- semantic headings must have logical hierarchy;
- buttons should be actual `<button>` elements;
- links should be actual `<a>` elements;
- icon-only controls need accessible names;
- decorative animation needs `aria-hidden="true"` where appropriate;
- motion-heavy sections need a reduced-motion alternative;
- text contrast must remain readable;
- touch targets must be comfortably usable.

## Reduced motion

Implement:

```css
@media (prefers-reduced-motion: reduce) {
  *,
  *::before,
  *::after {
    animation-duration: 0.01ms !important;
    animation-iteration-count: 1 !important;
    scroll-behavior: auto !important;
    transition-duration: 0.01ms !important;
  }
}
```

For premium experiences, go further: remove decorative cursor particles and replace cinematic transitions with clean opacity changes.

Do not rely on a blanket CSS reset alone if the motion is implemented in JavaScript/canvas.

---

# 20. Performance

Google-quality visual polish must not require a gaming PC.

## Rules

1. Prefer CSS transforms/opacity for animation.
2. Animate compositor-friendly properties.
3. Use one canvas for many particles instead of hundreds of DOM nodes.
4. Lazy-load below-the-fold images and videos.
5. Use responsive image sources.
6. Avoid giant uncompressed hero videos.
7. Do not run pointer listeners that trigger synchronous layout on every frame.
8. Use `requestAnimationFrame` for custom pointer/particle loops.
9. Cap particle count based on viewport size and device capability.
10. Pause offscreen animations.

## Pointer loop pattern

```js
let targetX = 0;
let targetY = 0;
let x = 0;
let y = 0;

window.addEventListener('pointermove', (event) => {
  targetX = event.clientX;
  targetY = event.clientY;
}, { passive: true });

function loop() {
  x += (targetX - x) * 0.12;
  y += (targetY - y) * 0.12;

  document.documentElement.style.setProperty('--cursor-x', `${x}px`);
  document.documentElement.style.setProperty('--cursor-y', `${y}px`);

  requestAnimationFrame(loop);
}

loop();
```

Use CSS custom properties to avoid rewriting large style strings.

---

# 21. Responsive design

Do not make a desktop site smaller. Re-compose it.

## Desktop

Use:

- very large display typography;
- wide editorial grids;
- spacious navigation;
- horizontal card rails;
- ambient pointer effects.

## Tablet

Reduce:

- headline size;
- horizontal nav density;
- card count in one row;
- particle density.

## Mobile

Change composition:

- stack hero content;
- collapse navigation;
- use larger tap targets;
- remove cursor-specific effects;
- simplify particle systems;
- shorten paragraphs;
- preserve the hero’s emotional impact through typography and spacing.

Example:

```css
@media (max-width: 720px) {
  .hero-title {
    font-size: clamp(2.75rem, 14vw, 5rem);
    line-height: 0.98;
    letter-spacing: -0.04em;
  }

  .hero-actions {
    flex-direction: column;
    align-items: stretch;
  }

  .hero-actions > * {
    width: 100%;
  }
}
```

---

# 22. Component grammar

Build a small set of highly reusable primitives.

Recommended primitives:

```text
Page
Container
Section
Header
NavItem
Dropdown
Button
IconButton
Badge
TextLink
Hero
MediaCard
VideoCard
BlogCard
FeatureGrid
StorySection
LogoMark
ParticleField
Footer
```

The important rule is that primitives should share tokens.

Do not give every component its own:

- radius;
- shadow;
- font;
- spacing scale;
- random transition.

---

# 23. Footer

The supplied recording shows an editorial footer rather than a conventional boxed footer.

Key characteristics:

- large brand/closing phrase;
- sparse two-column link groups;
- very large typographic brand expression;
- minimal legal/navigation row at the bottom.

Use this pattern when the product is marketing-heavy.

Example structure:

```text
Closing statement

Product                    Resources
Download                   Blog
Product                    Pricing
Docs                       Use Cases
Changelog
Press
Releases

[large brand wordmark / closing visual]

Brand                     About   Products   Privacy   Terms
```

The bottom should feel like the page has **resolved**, not simply “ended.”

---

# 24. Brand marks and logos

Never redraw a real brand logo approximately from memory.

Use:

- official asset when licensed/appropriate;
- exact vector supplied by the project;
- a neutral product mark when building a generic imitation.

The design skill may reproduce **principles** such as multicolor dots, rounded letterforms and motion language, but must not imply that a third-party site is actually Google.

---

# 25. Google-style copywriting

Visual style fails when copy sounds like generic SaaS.

Prefer:

- short sentences;
- direct verbs;
- clear nouns;
- confident but not loud language;
- one idea per line where appropriate;
- “show, then explain.”

Good:

> Build faster with agents that can actually work.

Less effective:

> Our innovative, cutting-edge next-generation platform enables organizations to unlock powerful AI-driven workflows at scale.

Do not write empty superlatives.

---

# 26. Microcopy for interaction

Button labels should answer “what happens?”

Prefer:

- Download
- Explore use cases
- Learn more
- Read blog
- Get started
- Watch demo

Avoid:

- Click here
- Submit
- Proceed
- Discover amazing things

Use the shortest label that remains unambiguous.

---

# 27. Advanced “fascination” effects

These are optional. They should be used as **signature moments**, not everywhere.

## 27.1 Elastic text reveal

A headline enters from a tiny vertical offset and resolves with slight easing. No bounce.

Sensation:

**precision + modernity.**

## 27.2 Intelligent particle response

Particles subtly move according to:

- pointer velocity;
- scroll velocity;
- section state.

Do not have each particle behave independently in a chaotic way. Use a field model so the whole group feels like one living system.

## 27.3 Icon state morph

Use a Material Symbols fill transition or a carefully designed SVG morph.

Examples:

- save → saved;
- play → pause;
- search → close;
- menu → close.

The transition should communicate state rather than simply look impressive.

## 27.4 Soft “intelligence pulse”

For an AI action:

1. user presses the action;
2. button compresses;
3. icon transitions;
4. a tiny accent signal appears;
5. result surface enters.

Keep the entire sequence short enough to feel immediate.

## 27.5 Magnetic card spotlight

Cards can respond to pointer position through a tiny local radial gradient. Keep the physical card stationary or nearly stationary.

```css
.card {
  --mx: 50%;
  --my: 50%;

  background:
    radial-gradient(
      280px circle at var(--mx) var(--my),
      rgb(255 255 255 / 10%),
      transparent 65%
    ),
    var(--surface);
}
```

This creates polish without a full tilt effect.

## 27.6 Avoid “AI slop” motion

Never combine all of these by default:

- neon glow;
- glass blur;
- 3D tilt;
- rainbow gradient;
- cursor trail;
- excessive spring;
- rotating icons;
- scroll zoom;
- animated text scramble.

The result usually feels synthetic rather than Google-like.

---

# 28. Video and image choreography

For high-end marketing pages, media should enter as part of the narrative.

Recommended sequence:

```text
TEXT PROMISE
    ↓
VISUAL TEASE
    ↓
MOTION / DEMO
    ↓
EXPLANATION
    ↓
CTA
```

Do not present a video before the user knows why it matters.

## Image transitions

Useful patterns:

- masked reveal;
- crop shift;
- slight scale settle;
- blur-to-sharp only when it enhances the story;
- opacity crossfade.

Avoid:

- random 3D rotations;
- spinning image stacks;
- aggressive blur transitions.

---

# 29. Design tokens to maintain globally

Keep tokens in one place.

```css
:root {
  /* Color */
  --c-bg: #fff;
  --c-fg: #202124;
  --c-fg-strong: #0b0c0e;
  --c-fg-muted: #5f6368;
  --c-border: #dadce0;

  /* Brand */
  --c-blue: #4285f4;
  --c-red: #ea4335;
  --c-yellow: #fbbc04;
  --c-green: #34a853;

  /* Radius */
  --r-sm: 10px;
  --r-md: 16px;
  --r-lg: 24px;
  --r-xl: 32px;
  --r-pill: 999px;

  /* Space */
  --s-1: 4px;
  --s-2: 8px;
  --s-3: 12px;
  --s-4: 16px;
  --s-5: 20px;
  --s-6: 24px;
  --s-8: 32px;
  --s-10: 40px;
  --s-12: 48px;
  --s-16: 64px;
  --s-20: 80px;
  --s-24: 96px;
  --s-32: 128px;
  --s-40: 160px;

  /* Motion */
  --dur-fast: 120ms;
  --dur-ui: 180ms;
  --dur-med: 320ms;
  --dur-slow: 650ms;
  --ease-ui: cubic-bezier(.2,.8,.2,1);
  --ease-enter: cubic-bezier(.16,1,.3,1);
}
```

The purpose of tokens is consistency, not numerical worship. Adjust values as the interface is tested.

---

# 30. Implementation architecture

A modern stack could be:

```text
React / Next.js / Astro / Vue
        ↓
CSS variables + utility/component CSS
        ↓
Semantic HTML
        ↓
Material Symbols / SVG icon system
        ↓
Canvas or CSS for ambient effects
        ↓
IntersectionObserver for reveals
        ↓
requestAnimationFrame for pointer motion
```

Do not add a heavy animation library just because an effect is fashionable. Native CSS + small, well-written JS can reproduce most of the visual language.

Use a library when it clearly improves:

- timeline complexity;
- gesture support;
- scene synchronization;
- maintainability.

---

# 31. Engineering rules for AI coding agents

When an AI agent implements a Google-inspired design, it must not stop after reproducing the screenshot structure.

The agent should inspect and verify:

### Layout

- exact container width;
- vertical rhythm;
- grid relationships;
- section whitespace;
- alignment baselines;
- mobile composition.

### Typography

- typeface;
- font weight;
- line height;
- tracking;
- max line length;
- optical sizing.

### Color

- neutral hierarchy;
- border contrast;
- CTA contrast;
- accent frequency;
- light/dark behavior.

### Interaction

- hover;
- focus;
- press;
- loading;
- selected;
- disabled;
- error;
- success.

### Motion

- entrance timing;
- easing;
- stagger;
- scroll choreography;
- pointer effects;
- reduced motion.

### Media

- crop;
- poster;
- autoplay behavior;
- loading;
- playback affordance;
- responsive sizing.

### Accessibility

- keyboard;
- semantics;
- names;
- contrast;
- focus;
- motion preferences.

### Performance

- paint cost;
- layout thrash;
- animation frame rate;
- image payload;
- video payload;
- mobile CPU/GPU usage.

---

# 32. Pixel-inspection checklist

Before calling the interface finished, compare the implementation against the design/reference at several viewport sizes.

## Header

- [ ] logo/mark baseline aligned;
- [ ] nav spacing consistent;
- [ ] CTA height consistent;
- [ ] no accidental visual crowding;
- [ ] dropdown anchors exactly to trigger.

## Hero

- [ ] headline is the dominant object;
- [ ] line breaks look intentional;
- [ ] CTA grouping reads in priority order;
- [ ] ambient animation never hurts legibility;
- [ ] hero has enough negative space;
- [ ] load motion completes quickly.

## Sections

- [ ] section boundaries are understood without unnecessary boxes;
- [ ] headline/copy/media hierarchy is stable;
- [ ] cards share a visual system;
- [ ] images have deliberate cropping;
- [ ] repeated elements do not feel mechanically cloned.

## Footer

- [ ] closing statement feels substantial;
- [ ] link columns are easy to scan;
- [ ] brand lockup is visually grounded;
- [ ] legal links are low-emphasis but readable.

---

# 33. Anti-patterns — what to reject immediately

Reject a design that is:

- mostly gradients and little hierarchy;
- full of floating glass cards;
- excessively rounded;
- covered in shadows;
- using rainbow colors everywhere;
- using multiple unrelated icon sets;
- animating every element continuously;
- using a custom cursor that blocks normal interaction;
- using scroll hijacking for ordinary pages;
- hiding buttons behind clever interactions;
- using tiny gray text to imitate “minimalism”;
- relying on blurry glass as the only depth mechanism;
- filled with decorative AI sparkles without semantics;
- visually impressive but slow;
- inaccessible with keyboard or reduced motion;
- too close to a real Google trademarked interface when a neutral interpretation would be more appropriate.

---

# 34. Quality bar

A page is not “Google-like” because it has:

- Google colors;
- a pill button;
- a sans-serif font;
- Material icons.

It is Google-inspired when the **whole system behaves coherently**.

The final experience should communicate:

> “This is technically sophisticated, but I do not have to work hard to use it.”

That is the target.

---

# 35. Reference implementation pattern

A minimal hero implementation should look conceptually like this:

```html
<header class="site-header">
  <a class="brand" href="/" aria-label="Home">
    <span class="brand-mark" aria-hidden="true"></span>
    <span>Product</span>
  </a>

  <nav class="site-nav" aria-label="Primary">
    <a href="#product">Product</a>
    <a href="#use-cases">Use cases</a>
    <a href="#pricing">Pricing</a>
    <a href="#resources">Resources</a>
  </nav>

  <a href="#download" class="btn-primary">Download</a>
</header>

<main>
  <section class="hero" aria-labelledby="hero-title">
    <canvas class="particle-field" aria-hidden="true"></canvas>

    <div class="hero-mark" aria-hidden="true">...</div>

    <h1 id="hero-title" class="hero-title">
      Build with the next generation of intelligent tools
    </h1>

    <p class="hero-support">
      Clear, powerful tools for people who want to move from idea to outcome.
    </p>

    <div class="hero-actions">
      <a class="btn-primary" href="#download">Download</a>
      <a class="btn-secondary" href="#use-cases">Explore use cases</a>
    </div>
  </section>
</main>
```

Then progressively add:

1. type refinement;
2. spacing refinement;
3. hover/press states;
4. scroll reveals;
5. restrained ambient motion;
6. pointer enhancement;
7. responsive recomposition;
8. accessibility/performance validation.

Do not build the spectacular effects before the base hierarchy is correct.

---

# 36. Decision framework when unsure

When choosing between two designs, prefer the one that:

1. communicates faster;
2. has fewer competing focal points;
3. uses color more sparingly;
4. has stronger typography;
5. uses fewer but better animations;
6. preserves native browser behavior;
7. performs better on mobile;
8. remains understandable without motion;
9. has clearer semantic HTML;
10. feels calm before it feels flashy.

---

# 37. Specific visual observations from the supplied recording

The supplied screen recording was inspected at multiple points across an ~81-second capture. Important observed traits include:

### Google Search context

The recording begins in a dark Google Search result context, reinforcing the contrast between Google’s highly information-dense search UI and the extremely spacious marketing page reached afterward.

### Antigravity landing hero

Observed:

- white background;
- large black typography;
- compact multicolor product mark;
- centered hero composition;
- black pill CTA;
- light secondary pill CTA;
- small multicolor particle/dash system around the hero;
- extremely high negative-space ratio.

The emotional result is **high-tech without visual heaviness**.

### Feature section

A later section shows a large statement alongside spacious content and a row of circular/icon-like motifs. The icons are thin, simple, outlined and visually quiet. This suggests a useful design lesson: when the headline carries the weight, iconography can become a supporting rhythm.

### Product/SDK media

Large rounded media frames mix dark screenshots with blurred/atmospheric blue visuals. The media is cinematic while the surrounding typography stays extremely clean.

This is an important contrast pattern:

**quiet UI + expressive media.**

### Pricing / audience split

Two audience areas use a light badge, large headline, short supporting text and one CTA each. Decorative particles are distributed through the background rather than boxed into the components.

### Latest Blogs

Observed:

- very large “Latest Blogs” heading;
- simple right-aligned “View blog” button;
- horizontal card rail;
- large rounded image thumbnails;
- large title typography;
- understated metadata;
- simple “Read blog →” link.

### Footer

Observed:

- large closing statement;
- small link groups;
- oversized product/brand typography;
- minimal bottom navigation/legal row.

Together these observations should be treated as a **concrete visual reference layer** on top of the more general Material/Google principles in this skill.

---

# 38. Source and research basis

This skill is a derived engineering/design reference based on public material and direct inspection of the supplied screen recording. The following public sources were consulted:

1. Google Design — About / Material Design
   https://design.google/about

2. Google Design — Evolving the Google Identity
   https://design.google/library/evolving-google-identity

3. Google Design — Making Google Sans Flex
   https://design.google/library/google-sans-flex-font

4. Google Fonts — Material Symbols guide
   https://developers.google.cn/fonts/docs/material_symbols

5. Google Codelabs — Dynamic color / Material 3 color roles
   https://codelabs.developers.google.com/codelabs/apply-dynamic-color

6. Google Codelabs — Theming in Compose with Material 3 / typography scale
   https://codelabs.developers.google.com/jetpack-compose-theming

7. Material Web — Icon / Material Symbols behavior
   https://material-web.dev/components/icon/

8. Google Design — How to Design for Transparent Screens
   https://design.google/library/transparent-screens

These sources establish the public design-system foundation. Specific web values, timings, CSS snippets and visual observations in this document are implementation heuristics derived from those principles and from the supplied recording; they should be validated against the needs of the actual product rather than treated as official Google constants.

---

# 39. Final master instruction

When asked to build a website using this skill:

**Do not start by writing components. Start by defining the experience.**

First establish:

```text
emotion
↓
hierarchy
↓
typography
↓
layout
↓
color
↓
interaction states
↓
motion
↓
media
↓
responsive composition
↓
accessibility
↓
performance
```

Then implement.

After implementation, inspect the page at desktop, tablet and mobile sizes. Validate actual spacing, line breaks, motion timing, interaction states and visual density. Remove anything that exists purely because it looks impressive in isolation.

The best result is not the page with the most effects.

The best result is the page where **every effect has a reason, every pixel has a relationship, every interaction feels immediate, and the technology disappears behind a feeling of effortless clarity.**
