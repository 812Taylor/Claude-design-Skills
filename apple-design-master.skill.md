---
name: apple-design-master
description: A rigorous Apple-inspired design system and implementation skill for creating exceptionally polished web interfaces. Covers visual hierarchy, typography, color, materials, Liquid Glass-inspired surfaces, spacing, icons, buttons, motion, interaction, accessibility, responsive behavior, emotional design, content strategy, validation, and implementation rules. Use this skill when a user asks for an Apple-like, premium, calm, precise, elegant, highly polished interface.
---

# Apple Design Master Skill

## 0. Mission

Build interfaces that feel:

- calm rather than noisy
- premium rather than expensive-looking
- precise rather than sterile
- confident rather than aggressive
- simple without being empty
- expressive without being decorative
- cinematic where appropriate
- tactile where interaction benefits from it
- familiar enough to understand immediately
- surprising only where the surprise improves comprehension or delight

The goal is **not** to copy Apple pixel-for-pixel.

The goal is to understand and reproduce the underlying design logic that makes Apple's interfaces feel coherent: hierarchy, restraint, typography, material behavior, motion, interaction feedback, content-first composition, semantic color, accessibility, and obsessive attention to detail.

This skill is primarily for **web UI**, while borrowing principles from Apple's public Human Interface Guidelines and current Apple platform design language. Web implementation must remain appropriate to the browser rather than pretending to be native iOS.

---

# 1. Source of Truth and Scope

When this skill conflicts with a project's actual requirements, accessibility requirements, browser constraints, or product usability, prioritize those requirements.

When a decision is uncertain:

1. Prefer Apple's public Human Interface Guidelines.
2. Prefer official Apple design resources and SF Symbols guidance.
3. Prefer the actual product's content and user goal.
4. Prefer accessibility and legibility over visual tricks.
5. Prefer restraint over adding another effect.
6. Validate the result at multiple viewport sizes.
7. Never assume that "Apple-like" means "white background + rounded corners".

Apple's public guidance emphasizes intuitive, familiar interactions, accessibility, semantic color, typography, platform-appropriate controls, and deliberate motion. Apple's current design language also places strong emphasis on materials, depth, content prominence, and adaptive interfaces.

Useful official references:

- Human Interface Guidelines:
  https://developer.apple.com/design/human-interface-guidelines/
- Apple Design:
  https://developer.apple.com/design/
- Apple Design Resources:
  https://developer.apple.com/design/resources/
- SF Symbols:
  https://developer.apple.com/sf-symbols/
- Apple Design Principles / WWDC:
  https://developer.apple.com/videos/play/wwdc2026/250/

Do not treat any single screenshot, website, or marketing page as a complete specification. Apple changes details over time.

---

# 2. Core Design Philosophy

## 2.1 Design is intentional omission

A premium interface is often defined by what is absent.

Before adding an element, ask:

- Does it improve comprehension?
- Does it improve navigation?
- Does it improve confidence?
- Does it improve discoverability?
- Does it create useful feedback?
- Does it create meaningful delight?
- Does it support the product's identity?

If the answer is no, remove it.

### Anti-pattern

Adding:

- gradients because gradients are fashionable
- shadows because cards need "depth"
- animations because the page should "feel alive"
- icons because empty space feels wrong
- badges because the interface looks too simple
- glass because Apple uses glass
- rounded corners to every element
- multiple competing accent colors

This produces imitation rather than design.

---

# 3. Emotional Target

Every page should have an intended emotional state.

Choose one primary emotional outcome and at most two supporting emotions.

Examples:

| Product | Primary feeling | Supporting feelings |
|---|---|---|
| Premium hardware | desire | confidence, curiosity |
| Finance dashboard | control | trust, clarity |
| AI product | possibility | intelligence, calm |
| Security product | safety | authority, confidence |
| Creative tool | freedom | playfulness, mastery |
| Luxury product | desire | exclusivity, calm |
| Productivity tool | control | momentum, focus |

## Emotional design rule

Do not attempt to make the interface exciting at every moment.

A strong experience alternates:

**calm → focus → anticipation → reward → calm**

That rhythm is more sophisticated than constant motion.

---

# 4. The Apple Feeling

The "Apple feeling" is not one visual property.

It is the combined effect of:

1. exceptionally clear hierarchy
2. controlled typography
3. generous negative space
4. deliberate imagery
5. minimal competing UI
6. consistent geometry
7. semantic color
8. high-quality iconography
9. subtle depth
10. physically plausible motion
11. strong interaction feedback
12. responsive adaptation
13. accessibility
14. content-first composition
15. obsessive consistency

A useful mental model:

> Remove everything that doesn't help. Then make everything that remains feel intentional.

---

# 5. Visual Hierarchy

Every viewport needs a clear hierarchy.

## Primary

The thing the user should notice first.

Usually:

- hero product
- headline
- main action
- important status

## Secondary

The thing understood immediately after the primary.

Examples:

- supporting description
- product benefit
- price
- secondary action

## Tertiary

Details that reward attention without competing with the main message.

Examples:

- specifications
- legal copy
- metadata
- subtle navigation
- footnotes

### Hierarchy test

Squint at the interface.

If five things compete equally, hierarchy has failed.

A successful page should remain understandable when viewed at low detail.

---

# 6. Composition

## 6.1 Think in visual stages

A premium landing page often follows:

1. arrival
2. statement
3. visual proof
4. explanation
5. interaction
6. comparison
7. action
8. details

Each stage should have a reason to exist.

## 6.2 Section rhythm

Avoid making every section identical.

Instead alternate:

- dark / light
- image-led / text-led
- dense / spacious
- static / interactive
- centered / asymmetric

But changes must feel intentional.

The user should experience progression rather than a collection of cards.

---

# 7. Negative Space

Negative space is an active design element.

Do not treat empty space as unused space.

Use it to:

- isolate important content
- increase perceived importance
- slow down the experience
- create anticipation
- separate semantic groups
- make premium imagery breathe

## Premium spacing heuristic

When something feels cramped:

1. reduce content
2. increase spacing
3. simplify typography
4. only then consider changing component dimensions

Do not automatically shrink everything to make it fit.

---

# 8. Spacing System

Use a systematic spacing scale rather than arbitrary values.

Recommended web baseline:

```text
4
8
12
16
20
24
32
40
48
64
80
96
120
144
160
192
240
```

Use the smaller values inside components.

Use larger values between semantic sections.

## Typical relationships

- icon ↔ label: 6–10px
- label ↔ supporting text: 4–8px
- button horizontal padding: 16–24px
- button vertical padding: 10–14px
- card internal padding: 20–32px
- section internal spacing: 64–160px
- major hero spacing: 96–240px depending on viewport

Do not force every dimension onto a grid if doing so harms visual balance.

---

# 9. Geometry

Apple-like geometry tends to feel deliberate rather than excessively rounded.

Do not apply `border-radius: 9999px` to everything.

Use shape according to semantic role.

Suggested starting points:

```text
small controls: 8–12px
cards: 16–24px
large media: 24–32px
pill controls: 999px
full-screen surfaces: 0–32px depending on context
```

The exact radius should respond to:

- component size
- visual weight
- platform
- content density
- surrounding geometry

Large objects can tolerate larger radii because their curvature reads more gently.

---

# 10. Typography

Typography carries more of the design than decoration.

## 10.1 Primary font

For Apple-platform work, Apple's system typography uses San Francisco.

For web products, use a system-oriented stack when appropriate:

```css
font-family:
  -apple-system,
  BlinkMacSystemFont,
  "SF Pro Display",
  "SF Pro Text",
  "Helvetica Neue",
  Arial,
  sans-serif;
```

Do not assume the user has every font installed.

For a branded web experience, a custom typeface may be appropriate, but legibility must remain dominant.

## 10.2 Typography hierarchy

Example responsive scale:

```text
Hero:
64–96px desktop
44–64px tablet
36–48px mobile

Section headline:
40–64px desktop
32–48px mobile

Subheading:
22–32px

Body:
16–19px

Small:
13–15px

Micro:
11–13px
```

These are starting points, not laws.

## 10.3 Weight

Avoid making everything bold.

Typical roles:

```text
Hero: medium / semibold
Section heading: semibold
Body: regular
Secondary: regular
Metadata: regular / medium
Primary action: medium / semibold
```

Very thin text should not be used at small sizes.

## 10.4 Tracking

Large headlines may use slightly tighter tracking.

Example:

```css
letter-spacing: -0.02em;
```

Do not blindly apply negative tracking to body text.

## 10.5 Line length

Aim for comfortable reading width.

For body copy:

```text
55–75 characters per line
```

For marketing headlines:

shorter is often stronger.

A headline should communicate one idea.

---

# 11. Text Content

Apple-like writing is not merely short.

It is:

- direct
- confident
- understandable
- human
- benefit-oriented
- restrained

Avoid:

> Revolutionary next-generation AI-powered technology designed to completely transform your productivity.

Prefer:

> Work faster. Think clearer.

Then explain the mechanism below.

## Headline formula

A strong product statement often follows:

```text
[Product]
[Meaningful promise].
```

or:

```text
A better way to [job].
```

or:

```text
[Short emotional statement].
[Concrete proof].
```

Do not use hype if the visual already communicates quality.

---

# 12. Color

## 12.1 Color is semantic

Never use color merely because it looks nice.

Define roles:

```text
background
surface
surface-secondary
text-primary
text-secondary
text-tertiary
separator
accent
success
warning
error
info
focus
```

## 12.2 Neutral palette

A premium neutral interface often uses several extremely subtle tonal steps rather than one gray.

Example conceptual scale:

```text
Canvas: #FFFFFF
Subtle canvas: #F5F5F7
Surface: #FFFFFF
Surface elevated: rgba(255,255,255,.72)
Primary text: #1D1D1F
Secondary text: rgba(29,29,31,.68)
Tertiary text: rgba(29,29,31,.48)
Separator: rgba(0,0,0,.10)
```

These values are examples, not fixed Apple system values.

Do not hard-code platform system colors when building a native app. On web, establish your own semantic tokens.

## 12.3 Dark mode

Dark mode is not:

```text
white → black
black → white
```

Instead:

- reduce harsh contrast where appropriate
- preserve hierarchy
- adjust surface brightness by elevation
- preserve semantic accent colors
- re-check contrast
- avoid pure white body text over pure black unless intentional

Example:

```text
background: #000000
primary surface: #1C1C1E
secondary surface: #2C2C2E
primary text: rgba(255,255,255,.96)
secondary text: rgba(255,255,255,.68)
```

Again: treat these as starting tokens, not immutable Apple values.

---

# 13. Accent Color

One strong accent is usually better than many.

Accent color can communicate:

- primary action
- selected state
- focus
- links
- progress
- identity

Do not make every button colorful.

A premium interface often allows most of the UI to remain neutral so the accent becomes meaningful.

---

# 14. Gradients

Use gradients as lighting or atmosphere, not decoration.

Good gradient:

- supports depth
- guides attention
- reinforces product imagery
- creates a focal point

Bad gradient:

- exists only because flat color feels boring
- covers every surface
- reduces text contrast
- competes with product imagery

Use low-frequency gradients with subtle transitions.

---

# 15. Materials

Modern Apple design uses material as a way of creating hierarchy and continuity.

A material should communicate:

- what layer something occupies
- what is behind it
- whether it is interactive
- whether it floats
- whether it belongs to the system layer or content layer

## 15.1 Material stack

Think in layers:

```text
content
↓
surface
↓
translucent surface
↓
blur
↓
highlight
↓
shadow
```

But do not use all layers automatically.

## 15.2 Glass

A glass-like surface may use:

```css
background: rgba(255,255,255,.68);
backdrop-filter: blur(20px) saturate(180%);
-webkit-backdrop-filter: blur(20px) saturate(180%);
border: 1px solid rgba(255,255,255,.30);
box-shadow:
  0 1px 2px rgba(0,0,0,.06),
  0 12px 40px rgba(0,0,0,.10);
```

However:

- glass must have meaningful content behind it
- blur must improve hierarchy
- text must remain readable
- do not stack glass on glass endlessly
- do not make every button translucent
- use opacity and blur carefully

## 15.3 Liquid Glass-inspired rule

The current Apple language emphasizes material that interacts with content rather than simply looking like frosted plastic.

Therefore:

**material should feel responsive to its environment.**

When an object moves over a colorful background, its material should remain legible while retaining contextual depth.

---

# 16. Depth

Depth should be hierarchical.

Use:

1. no depth for background
2. subtle separation for surfaces
3. moderate depth for floating controls
4. stronger depth for temporary overlays

Do not use enormous shadows.

### Better shadow model

Instead of:

```css
box-shadow: 0 30px 100px black;
```

prefer layered, low-opacity shadows:

```css
box-shadow:
  0 1px 2px rgba(0,0,0,.08),
  0 8px 24px rgba(0,0,0,.08),
  0 24px 60px rgba(0,0,0,.06);
```

Tune according to background.

---

# 17. Borders and Separators

Borders should usually separate rather than decorate.

Prefer:

```css
border: 1px solid rgba(0,0,0,.08);
```

over dark, high-contrast outlines.

For dark surfaces:

```css
border: 1px solid rgba(255,255,255,.10);
```

Use separators only where grouping benefits from them.

If spacing already clearly separates two sections, a line may be unnecessary.

---

# 18. Icons

Iconography must feel like one language.

Use a consistent icon source whenever possible.

For Apple-platform concepts, SF Symbols are the reference language. SF Symbols are designed to integrate with San Francisco, support multiple weights and scales, and include animation and rendering behaviors.

For the web:

- use a coherent icon family
- use consistent stroke/fill logic
- align optical weight with text
- avoid mixing random icon libraries
- avoid emoji as UI icons unless explicitly appropriate

## Icon size

Typical web starting points:

```text
12–14px: micro
16px: compact
18px: default
20–24px: prominent
28–32px: hero/supporting
```

Never judge an icon solely by bounding-box size.

Judge by optical size.

---

# 19. Icon Weight

The icon should visually match the text.

For example:

```text
14px text → light/regular icon
16px text → regular icon
18px semibold text → medium icon
```

Do not pair a very heavy icon with delicate typography.

---

# 20. Buttons

Buttons are promises.

A button should make the result of clicking it predictable.

## 20.1 Primary button

Typical characteristics:

- strong contrast
- clear label
- medium/semibold text
- comfortable touch target
- subtle radius
- restrained shadow
- immediate feedback

Example:

```text
height: 44–52px
padding-x: 18–24px
radius: 999px or 12–14px
```

Choose pill vs rounded rectangle based on product language.

## 20.2 Secondary button

Use:

- neutral surface
- outline
- or lower-emphasis material

It should remain obviously interactive.

## 20.3 Tertiary button

Often:

- text
- icon + text
- subtle hover
- no heavy container

## 20.4 Button labels

Prefer action-oriented wording:

```text
Buy
Learn more
View details
Start free
Continue
Save
```

Avoid vague:

```text
Click here
Go
More
Submit
```

## 20.5 Icon-only buttons

Use only when the icon is familiar.

Provide:

- accessible name
- tooltip where appropriate
- adequate hit area
- visible focus state

---

# 21. Button Microinteractions

A good button has states:

```text
rest
hover
focus
pressed
disabled
loading
success
error
```

### Hover

Subtle changes:

- brightness
- background opacity
- tiny elevation
- tiny scale, if appropriate

Avoid dramatic scaling.

Example:

```css
transform: translateY(-1px);
```

### Pressed

The button should feel closer to the pointer/finger:

```css
transform: scale(.98);
```

Duration should be short.

### Loading

Do not replace the entire interface with a spinner unless necessary.

Prefer:

```text
button stays in place
label remains recognizable
progress indicator appears
```

### Success

A successful action can use:

- icon morph
- checkmark
- subtle color change
- content transition

Avoid confetti unless celebration is actually part of the product.

---

# 22. Motion

Motion is a communication system.

Every animation should answer:

**Why is this moving?**

Valid answers:

- state changed
- user initiated movement
- hierarchy changed
- object appeared/disappeared
- relationship changed
- system needs to communicate progress
- motion creates meaningful delight

Invalid answer:

> Because it looks cool.

---

# 23. Motion Principles

## Continuity

The object that changes should visually remain connected to what it becomes.

## Spatial consistency

If an element expands, it should expand from a believable origin.

## Responsiveness

User-driven interactions should respond immediately.

## Restraint

Do not animate every property.

## Choreography

Multiple elements should move with coordinated timing.

---

# 24. Timing

Useful starting points:

```text
micro feedback: 80–140ms
small transition: 160–240ms
standard transition: 240–400ms
large transition: 400–700ms
cinematic transition: 700–1200ms
```

Use shorter durations for direct manipulation.

Use longer durations for narrative transitions.

---

# 25. Easing

Avoid default linear motion for interface transitions.

Use:

- ease-out for elements entering
- ease-in for elements leaving
- spring-like curves for tactile interactions
- carefully tuned cubic-bezier curves for web transitions

Example:

```css
cubic-bezier(.22, 1, .36, 1)
```

This is a starting point, not a universal Apple curve.

---

# 26. Springs

Spring motion can communicate physicality.

Conceptually:

```text
high stiffness
low visible overshoot
low damping variation
```

The user should feel:

> the interface responded

not:

> the interface bounced.

Avoid excessive bounce.

---

# 27. Scroll Motion

Scroll-linked animation should reward movement rather than fight it.

Good:

- image scale subtly changes
- text fades into hierarchy
- product rotates slowly
- sections reveal progressively
- navigation changes material state

Bad:

- content moves independently of scrolling
- excessive parallax
- large text constantly flying around
- scroll hijacking
- mandatory horizontal scrolling

---

# 28. Reduced Motion

Always respect:

```css
@media (prefers-reduced-motion: reduce)
```

Reduce:

- parallax
- scale animations
- repeated loops
- large movement
- decorative motion

Replace complex transitions with:

- opacity
- simple state change
- minimal movement

Accessibility is part of the design, not a post-processing step.

---

# 29. Hover Is Not Touch

Never design the experience around hover alone.

For web:

```text
desktop:
hover + focus + click

mobile:
tap + press + scroll
```

Every hover-only behavior needs a non-hover alternative.

---

# 30. Navigation

Navigation should feel almost invisible until needed.

Use:

- strong spacing
- minimal labels
- familiar icons
- consistent placement
- predictable transitions

Do not overload the top navigation.

For mobile:

- prioritize the most important actions
- hide secondary complexity behind familiar patterns
- preserve a stable navigation structure

---

# 31. Sticky Navigation

A premium sticky navigation often changes state when the user scrolls.

Example:

At top:

```text
transparent / content-integrated
```

After scrolling:

```text
translucent material
blur
subtle border
slightly stronger contrast
```

The transition should be quiet.

Do not abruptly snap between unrelated visual states.

---

# 32. Hero Sections

The hero is the most emotionally expensive section of the page.

It should answer quickly:

1. What is this?
2. Why should I care?
3. What should I do?

A premium hero often uses:

```text
small eyebrow
large headline
supporting sentence
primary CTA
secondary CTA
hero visual
```

But do not include all five automatically.

If the product visual already explains the product, let the visual do work.

---

# 33. Product Imagery

Apple-style product imagery often uses:

- controlled lighting
- high contrast where appropriate
- clean silhouette
- carefully selected perspective
- strong negative space
- realistic reflections
- subtle depth
- cinematic backgrounds

Do not put text over the most important visual detail.

Let the object breathe.

---

# 34. Image Cropping

Cropping is part of composition.

Do not simply use:

```css
object-fit: cover;
```

and call the job finished.

Check:

- focal point
- subject position
- mobile crop
- desktop crop
- text overlap
- safe zones
- visual balance

Use different focal positions at different breakpoints when necessary.

---

# 35. Responsive Design

Responsive design is not:

```text
desktop × .5
```

It is re-composition.

At mobile:

- reduce navigation
- change alignment
- shorten copy
- resize typography
- stack actions
- simplify decorative elements
- preserve touch targets
- rethink image crops

At desktop:

- exploit whitespace
- increase composition
- introduce asymmetry
- use wider media
- increase visual storytelling

---

# 36. Breakpoints

Do not design only around device names.

Design around layout failure.

Starting points:

```text
< 480px  mobile
480–767px large mobile
768–1023px tablet
1024–1279px desktop
1280–1535px large desktop
1536px+ ultra-wide
```

But use container logic and CSS clamp rather than hard-coded device assumptions.

---

# 37. Container Width

A common premium web layout:

```css
max-width: 1200px;
margin-inline: auto;
padding-inline: 24px;
```

For content-heavy pages, use narrower reading widths.

For cinematic product sections, allow wider compositions.

---

# 38. Accessibility

Accessibility is not optional.

Apple's public guidance emphasizes:

- perceivable interfaces
- adaptable interfaces
- familiar and consistent interactions
- larger text support
- contrast
- non-color-only communication
- accessible controls
- VoiceOver / screen-reader support
- reduced motion

For web implementation, additionally verify:

- keyboard navigation
- semantic HTML
- visible focus
- ARIA only where needed
- logical tab order
- reduced motion
- contrast
- zoom/reflow
- screen reader naming

---

# 39. Touch Targets

For touch interfaces, Apple guidance uses 44×44 pt as a common default control size on iOS/iPadOS.

For web:

Aim for approximately:

```text
44×44 CSS px
```

when practical.

If the visible icon is 20px, the hit area can still be 44px.

Do not make the icon itself unnecessarily large.

---

# 40. Focus States

Never remove focus outlines just to make the UI cleaner.

A premium focus state can be subtle:

```css
outline: 2px solid currentColor;
outline-offset: 3px;
```

or a semantic ring.

Focus should be:

- visible
- consistent
- high contrast
- not dependent on color alone

---

# 41. Accessibility Contrast

As a practical baseline, verify WCAG contrast.

Apple's accessibility documentation references WCAG AA guidance such as:

- 4.5:1 for smaller text
- 3:1 for larger text
- 3:1 for bold larger text

Do not assume that a gray "looks readable" because it looks good in a design mockup.

Test it.

---

# 42. Semantic Color

Never communicate a state using color alone.

Bad:

```text
green = good
red = bad
```

Better:

```text
green + check icon + "Complete"
red + warning icon + "Payment failed"
```

Color reinforces meaning.

It should not carry the entire meaning.

---

# 43. Forms

Forms should feel calm.

Use:

- clear labels
- generous spacing
- obvious focus
- predictable validation
- inline error messaging
- minimal decorative borders

Do not wait until form submission to explain obvious errors.

---

# 44. Inputs

A refined input typically has:

```text
label
input area
optional hint
validation state
```

Avoid placeholder-only labels.

Placeholder text disappears and harms context.

---

# 45. Error Design

Errors should communicate:

1. what happened
2. why it happened, if known
3. what the user can do next

Bad:

> Invalid input.

Better:

> Enter a valid email address.

Best when appropriate:

> That email doesn't look right. Check the address and try again.

Do not blame the user.

---

# 46. Loading

A loading state should preserve layout.

Avoid layout jumps.

Use:

- skeletons when structure matters
- progress indicators when progress can be estimated
- subtle activity indicators for short operations

Avoid fake progress.

Never animate indefinitely without purpose.

---

# 47. Empty States

An empty state is a product moment.

Explain:

- what is missing
- why it matters
- what the user can do

Do not fill the screen with decorative illustration if the next action is obvious.

---

# 48. Modals and Sheets

Use overlays for:

- focused tasks
- confirmation
- temporary context
- detail views

Avoid modals for simple information that could live inline.

A modal should feel like a temporary layer, not a second website.

Use:

- backdrop
- strong hierarchy
- clear dismissal
- keyboard Escape
- focus management
- mobile adaptation

---

# 49. Bottom Sheets

On mobile, bottom sheets can feel natural because they preserve context.

Motion:

```text
origin = bottom
enter = translateY(100%) → 0
exit = 0 → translateY(100%)
```

Add subtle opacity to the backdrop.

Do not make the sheet bounce excessively.

---

# 50. Cards

Cards are frequently overused.

Ask:

> Does this content actually belong to a separate object?

If not, use spacing instead.

Use cards when they provide:

- grouping
- interaction
- comparison
- hierarchy
- containment

Do not put every sentence into a rounded rectangle.

---

# 51. Lists

Lists are often more elegant than cards.

Use list rows when users need to:

- scan
- compare
- select
- navigate

Use:

```text
leading icon
title
supporting text
trailing value/action
```

Maintain consistent alignment.

---

# 52. Dividers

Prefer whitespace when possible.

Use dividers when:

- list rows need separation
- content groups need explicit boundaries
- a visual rule improves scanning

Keep them subtle.

---

# 53. Tables

Tables should prioritize:

1. comparison
2. alignment
3. scan speed

Avoid excessive borders.

Use subtle row separation and strong column alignment.

---

# 54. Data Visualization

Do not make charts decorative.

Use:

- restrained colors
- clear labels
- semantic emphasis
- accessible patterns
- meaningful interaction

If a chart requires a legend to understand basic information, reconsider the encoding.

---

# 55. Search

Search should feel immediate.

Use:

- familiar magnifying-glass icon
- clear input state
- keyboard shortcut where appropriate
- result feedback
- empty/error states

Do not hide critical search affordances behind obscure interactions.

---

# 56. Icon + Text Rules

Use icon + text when:

- action may be unfamiliar
- accessibility benefits from explicit labeling
- icon alone is ambiguous

Use icon alone when:

- action is universally recognizable
- space is constrained
- surrounding context makes the meaning obvious

---

# 57. Microcopy and Delight

Delight should emerge from competence.

Examples:

- a button responds instantly
- an item slides naturally into position
- a success state feels satisfying
- a product image subtly transforms
- a transition preserves spatial continuity

Do not force delight with:

- confetti
- random particles
- excessive sound
- bouncing text
- constant gradients

---

# 58. The Psychology of Premium UI

Premium perception often comes from:

### Consistency
The brain perceives control.

### Restraint
The brain perceives confidence.

### Responsiveness
The brain perceives intelligence.

### Smooth motion
The brain perceives physical coherence.

### High-quality imagery
The brain perceives craftsmanship.

### Whitespace
The brain perceives importance.

### Clear hierarchy
The brain perceives competence.

### Predictability
The brain perceives safety.

The combination creates trust.

---

# 59. The "Fascination" Layer

If the goal is to make a website feel fascinating, use a controlled reveal system.

## Layer 1 — Immediate clarity

The user understands the product.

## Layer 2 — Visual curiosity

A beautiful object, composition, or movement invites further exploration.

## Layer 3 — Interaction reward

Scrolling or hovering reveals meaningful information.

## Layer 4 — Discovery

The user notices details they didn't see initially.

## Layer 5 — Mastery

Repeated use becomes faster and more satisfying.

This creates fascination without sacrificing usability.

---

# 60. Scroll Storytelling

A high-end product page can use scroll as a narrative.

Example:

```text
0%:
hero product appears

15%:
product moves into focus

30%:
feature becomes visible

45%:
detail changes

60%:
technical explanation

75%:
comparison

90%:
CTA

100%:
support/details
```

Every scroll-linked animation must have a semantic reason.

---

# 61. Scroll Choreography

When multiple elements animate:

```text
background → first
main object → second
headline → third
supporting detail → fourth
CTA → last
```

Do not animate everything simultaneously.

Use temporal hierarchy.

---

# 62. Parallax

Use parallax subtly.

Recommended principle:

> The user should notice the atmosphere before they notice the implementation.

If someone says:

> Wow, that element is moving at a different speed.

the effect may be too strong.

---

# 63. Cursor Effects

Cursor effects are optional.

Good:

- magnetic button behavior
- subtle hover spotlight
- precise pointer feedback

Bad:

- huge cursor replacements
- cursor trails everywhere
- effects that hide the actual pointer
- cursor-dependent navigation

Never make essential information depend on a custom cursor.

---

# 64. Magnetic Buttons

If used:

- keep movement small
- preserve click target
- never move the button unexpectedly far
- disable on touch
- avoid causing layout shift

Conceptual range:

```text
translation: 2–8px
```

---

# 65. Hover Lighting

A subtle radial gradient can follow the pointer:

```css
background:
  radial-gradient(
    300px circle at var(--x) var(--y),
    rgba(255,255,255,.12),
    transparent 45%
  );
```

Use it only where material or depth benefits.

---

# 66. Glass + Motion

If a glass surface moves:

- blur should remain stable
- content should not flicker
- backdrop-filter should not cause visual artifacts
- borders should remain coherent
- contrast must survive the background change

Test on mobile Safari and lower-powered devices.

---

# 67. Performance

Premium animation that stutters is not premium.

Prefer:

```text
transform
opacity
filter, used carefully
```

Avoid expensive layout animation when possible:

```text
width
height
top
left
margin
```

Use `transform` for movement.

Use `will-change` sparingly.

Do not optimize every element prematurely.

---

# 68. Reduced CPU/GPU Complexity

A visual effect is not automatically valuable because it is expensive.

If the effect does not materially improve:

- hierarchy
- feedback
- emotion
- comprehension

remove it.

---

# 69. Browser Reality

Test:

- Safari
- Chrome
- Firefox
- mobile Safari
- mobile Chrome

Particularly verify:

- backdrop-filter
- sticky positioning
- viewport units
- safe areas
- font rendering
- video autoplay
- scroll behavior
- touch events

---

# 70. Safe Areas

For mobile experiences that approach device edges:

```css
padding-bottom: env(safe-area-inset-bottom);
padding-top: env(safe-area-inset-top);
```

Do not let controls collide with system UI.

---

# 71. Navigation Bar Material

A web navigation bar can use:

```css
background: rgba(255,255,255,.72);
backdrop-filter: saturate(180%) blur(20px);
border-bottom: 1px solid rgba(0,0,0,.08);
```

But only if the visual context benefits from translucency.

A flat background may be more elegant on some pages.

---

# 72. Video

Apple-like marketing experiences frequently use video as a visual explanation.

Video should:

- load intelligently
- have a poster
- avoid blocking interaction
- respect reduced motion where relevant
- work without sound
- have controls when user-controlled
- preserve content meaning without audio

Do not use video merely as background decoration.

---

# 73. Video Transitions

Good transitions:

```text
fade
crossfade
scale
mask reveal
object continuity
```

Use object continuity when the same product appears across sections.

---

# 74. 3D and Product Rotation

3D can create fascination when it explains the object.

Use:

- controlled rotation
- realistic lighting
- depth
- material response

Do not rotate continuously without user meaning.

Interactive 3D should have an obvious interaction model.

---

# 75. Sound

Sound should be optional and intentional.

Never autoplay loud audio.

Use sound only when it meaningfully contributes to the experience.

---

# 76. Design Tokens

Every implementation should define tokens.

Example:

```css
:root {
  --color-bg: #fff;
  --color-surface: #f5f5f7;
  --color-text: #1d1d1f;
  --color-text-secondary: rgba(29,29,31,.68);
  --color-separator: rgba(0,0,0,.10);
  --color-accent: #0071e3;

  --radius-sm: 10px;
  --radius-md: 16px;
  --radius-lg: 24px;
  --radius-pill: 999px;

  --space-1: 4px;
  --space-2: 8px;
  --space-3: 12px;
  --space-4: 16px;
  --space-5: 24px;
  --space-6: 32px;
  --space-7: 48px;
  --space-8: 64px;
  --space-9: 96px;
  --space-10: 128px;

  --motion-fast: 140ms;
  --motion-standard: 280ms;
  --motion-slow: 500ms;

  --ease-standard: cubic-bezier(.22,1,.36,1);
}
```

These are design starting points, not Apple's proprietary token set.

---

# 77. Component Architecture

Build reusable components.

Recommended baseline:

```text
App
├── Header
├── Navigation
├── Hero
├── Section
│   ├── Heading
│   ├── Copy
│   └── Media
├── Button
├── IconButton
├── Card
├── List
├── Modal
├── Sheet
├── Footer
```

Each component should support states rather than duplicated markup.

---

# 78. Component State Matrix

For interactive components, explicitly design:

```text
default
hover
focus
pressed
disabled
loading
success
error
selected
expanded
collapsed
```

Do not design only the "pretty" default state.

---

# 79. State Transitions

A state transition should be understandable even if animation is disabled.

The visual state itself must communicate the change.

Motion reinforces the change.

It should never be the only explanation.

---

# 80. Interaction Rules

Every interaction should have:

```text
affordance
response
result
```

Example:

Button:

```text
affordance → visible button
response → press feedback
result → content changes
```

If any stage is missing, the interaction feels broken.

---

# 81. Perceived Speed

The user does not measure raw milliseconds.

They measure:

- response
- continuity
- uncertainty
- feedback

Therefore:

**instant feedback + clear progress often feels faster than a technically faster but silent operation.**

---

# 82. Skeleton Loading

Skeletons should resemble final layout.

Do not use random gray rectangles.

Skeletons should communicate:

> Something is loading here.

not:

> This is a collection of boxes.

---

# 83. Progressive Disclosure

Do not show every detail immediately.

Show:

```text
essential
↓
useful
↓
advanced
```

This keeps the first interaction simple without hiding power.

---

# 84. Complexity Budget

Every screen has a complexity budget.

Spend it on:

- product value
- interaction
- meaningful visuals

Do not spend it on:

- decorative shadows
- unnecessary cards
- redundant labels
- competing animations
- excessive navigation

---

# 85. Visual Noise Audit

Count:

- colors
- font sizes
- font weights
- border types
- radii
- shadows
- icon styles
- animation styles

If there are too many, consolidate.

A mature design system usually has fewer primitives than a beginner expects.

---

# 86. The One-Accent Rule

Start with:

```text
neutrals + one accent
```

Add another color only when it has a semantic reason.

This creates visual authority.

---

# 87. Premium White Space Rule

If a section feels cheap:

1. remove one element
2. increase space
3. strengthen hierarchy
4. improve image quality
5. only then consider decoration

---

# 88. Mobile-First Emotional Design

Mobile is not a compressed desktop.

Ask:

- What should the user see first?
- What should disappear?
- What should become sticky?
- What should become a sheet?
- What should become a full-width button?
- What can be delayed?

---

# 89. Desktop Emotional Design

Desktop offers:

- more horizontal space
- more visual staging
- more whitespace
- richer composition

Do not simply enlarge mobile content.

Use the additional space to improve storytelling.

---

# 90. Apple-like Footer

A footer can become information architecture.

Use:

- grouped navigation
- subtle typography
- restrained separators
- legal information
- language/region controls

Do not make the footer visually louder than the product.

---

# 91. Branding

Branding should support the experience rather than dominate it.

Apple's public guidance emphasizes that branding should defer to content.

For an Apple-inspired product:

- logo should be recognizable
- brand color should be deliberate
- typography should remain legible
- visual identity should coexist with familiar interaction patterns

---

# 92. Avoiding "AI-Looking" Design

The following often makes a site look AI-generated or generic:

- excessive gradients
- purple/blue glow everywhere
- random glass cards
- excessive rounded rectangles
- giant centered headline with no information
- floating blobs
- too many animated particles
- inconsistent icons
- meaningless 3D shapes
- excessive shadows
- every section having a different visual style

Apple-like quality requires **editing**, not decoration.

---

# 93. Image Prompting for Apple-Like Visuals

When generating imagery, prioritize:

```text
clean industrial design
controlled studio lighting
realistic materials
precise reflections
minimal composition
premium product photography
high micro-detail
soft atmospheric depth
large negative space
cinematic but restrained lighting
```

Avoid:

```text
fantasy glow
random neon
overly saturated colors
plastic-looking materials
excessive bloom
generic tech background
```

---

# 94. Product Photography Checklist

Check:

- silhouette
- reflections
- material
- edge highlights
- shadow
- contact with ground
- perspective
- focal length feel
- background
- color harmony
- crop
- scale

A single bad reflection can make a product render feel fake.

---

# 95. Icon Animation

Use icon animation to communicate state.

Examples:

```text
play → pause
plus → check
menu → close
heart → filled heart
download → completion
search → clear
```

Animation should preserve object identity.

This is especially effective with layered vector icons.

---

# 96. Micro-Feedback

Every important interaction should provide immediate evidence.

Examples:

- button darkens
- control depresses
- switch moves
- checkmark appears
- row highlights
- text changes
- progress begins

A 100ms response can dramatically improve perceived quality.

---

# 97. Delight Timing

Do not place delight before comprehension.

Correct:

```text
understand → interact → succeed → delight
```

Incorrect:

```text
animation → animation → animation → finally understand
```

---

# 98. Interaction Safety

For destructive actions:

- make consequences clear
- use confirmation where appropriate
- allow undo when possible
- avoid ambiguous buttons
- never hide destructive actions behind misleading labels

A premium interface feels safe.

---

# 99. Undo

Undo is often better than a confirmation dialog.

Instead of:

> Are you sure?

consider:

> Item deleted — Undo

when the action is safely reversible.

This keeps the experience fast.

---

# 100. Motion Accessibility Test

Run the interface with:

```text
prefers-reduced-motion: reduce
```

Then ask:

- Does the page still make sense?
- Are state changes visible?
- Is hierarchy preserved?
- Are interactions understandable?

If yes, motion is enhancing the experience rather than carrying it.

---

# 101. Keyboard Test

Use the interface without a mouse.

Test:

```text
Tab
Shift+Tab
Enter
Space
Escape
Arrow keys where relevant
```

The experience should remain coherent.

---

# 102. Screen Reader Test

Check:

- headings
- landmarks
- button names
- image alt text
- form labels
- status announcements
- modal focus
- hidden decorative content

Do not overuse ARIA.

Semantic HTML is the first choice.

---

# 103. Responsive QA Matrix

Minimum test sizes:

```text
375 × 812
390 × 844
430 × 932
768 × 1024
1024 × 768
1280 × 800
1440 × 900
1920 × 1080
```

Also test unusual intermediate widths.

---

# 104. Visual QA

Inspect at:

- 100%
- 200% zoom
- low brightness
- high brightness
- dark mode
- reduced motion
- slow network
- touch input
- keyboard navigation

---

# 105. Pixel-Level QA

Check:

- baseline alignment
- icon centering
- button height
- text wrapping
- image crop
- border consistency
- radius consistency
- shadow softness
- spacing rhythm
- animation timing

Do not obsess over individual pixels before fixing hierarchy.

---

# 106. "Apple Test"

Ask:

### 1. Does the interface look calm?
If not, reduce noise.

### 2. Is the most important thing obvious?
If not, improve hierarchy.

### 3. Does every effect have a reason?
If not, remove it.

### 4. Does interaction feel immediate?
If not, improve feedback.

### 5. Does motion feel physical?
If not, retune timing/easing.

### 6. Does the design work without motion?
If not, improve state communication.

### 7. Does it work on mobile?
If not, redesign rather than shrink.

### 8. Does it remain accessible?
If not, fix it before polishing.

### 9. Does it feel like one system?
If not, consolidate primitives.

### 10. Would removing something improve it?
If yes, remove it.

---

# 107. Build Workflow

Use this sequence.

## Phase 1 — Understand

Document:

```text
product
audience
primary task
emotional goal
brand personality
platform
viewport targets
content hierarchy
```

## Phase 2 — Establish tokens

Define:

```text
colors
type
spacing
radii
shadows
materials
motion
breakpoints
```

## Phase 3 — Build primitives

Create:

```text
Button
IconButton
Text
Input
Card
Navigation
Modal
Sheet
```

## Phase 4 — Build composition

Create:

```text
Header
Hero
Sections
Footer
```

## Phase 5 — Add motion

Only after static hierarchy is correct.

## Phase 6 — Add delight

Only after usability is correct.

## Phase 7 — Accessibility

Test:

```text
keyboard
screen reader
contrast
reduced motion
touch targets
zoom
```

## Phase 8 — Performance

Inspect:

```text
FPS
layout shifts
image size
video size
JavaScript
blur
shadows
```

## Phase 9 — Final polish

Tune:

```text
1–2px alignment
timing
opacity
tracking
cropping
microcopy
```

---

# 108. Design Review Checklist

Before calling a page finished, verify every category.

## Structure

- [ ] clear hierarchy
- [ ] clear content flow
- [ ] no unnecessary sections
- [ ] intentional whitespace
- [ ] consistent containers

## Typography

- [ ] correct hierarchy
- [ ] comfortable line lengths
- [ ] consistent weights
- [ ] correct tracking
- [ ] no tiny critical text

## Color

- [ ] semantic colors
- [ ] one clear accent
- [ ] sufficient contrast
- [ ] dark mode tested
- [ ] color not used as the only signal

## Icons

- [ ] one visual language
- [ ] consistent optical weight
- [ ] correct alignment
- [ ] accessible labels
- [ ] no unnecessary icons

## Buttons

- [ ] obvious purpose
- [ ] touch target
- [ ] hover
- [ ] focus
- [ ] pressed
- [ ] disabled
- [ ] loading
- [ ] success/error where needed

## Motion

- [ ] purposeful
- [ ] responsive
- [ ] coherent easing
- [ ] no excessive bounce
- [ ] reduced motion supported

## Materials

- [ ] glass only where useful
- [ ] readable through blur
- [ ] depth hierarchy
- [ ] no excessive shadows

## Mobile

- [ ] composition redesigned
- [ ] navigation works
- [ ] touch targets
- [ ] image crops
- [ ] text wraps
- [ ] no horizontal overflow

## Accessibility

- [ ] keyboard
- [ ] focus
- [ ] contrast
- [ ] screen reader
- [ ] reduced motion
- [ ] zoom/reflow
- [ ] semantic HTML

## Performance

- [ ] optimized images
- [ ] video optimized
- [ ] no unnecessary JS
- [ ] animation mostly transform/opacity
- [ ] blur tested
- [ ] no layout jumps

---

# 109. Final Quality Gate

Do not ship because:

> It looks good.

Ship when:

> The interface feels inevitable.

Meaning:

- nothing feels randomly placed
- nothing feels unnecessarily animated
- nothing feels confusing
- nothing feels visually inconsistent
- every important action is obvious
- the visual hierarchy survives mobile
- accessibility does not feel bolted on
- motion reinforces meaning
- the product feels confident
- the user can focus on the content

---

# 110. Master Rule

When designing an Apple-inspired interface, repeatedly ask:

> What is the simplest possible interface that produces the strongest emotional and functional result?

Then:

1. remove noise
2. strengthen hierarchy
3. refine typography
4. refine spacing
5. refine imagery
6. refine interaction
7. add purposeful motion
8. validate accessibility
9. validate responsiveness
10. remove anything that still feels unnecessary

The final 10% of quality often comes from the smallest details:

- 2px alignment
- slightly better line-height
- a better crop
- a calmer shadow
- a more accurate icon
- a faster press response
- a cleaner transition
- one less border
- one less sentence
- one less visual effect

That is the craft.

---

# 111. Implementation Defaults

When the user says:

> "Make it Apple-like"

Do not automatically create:

- a white page
- blue buttons
- rounded cards
- giant San Francisco-like text
- glass everywhere
- gradients everywhere

Instead:

### Step 1
Identify the product's emotional goal.

### Step 2
Identify the single most important content.

### Step 3
Build the hierarchy around that content.

### Step 4
Choose neutral surfaces.

### Step 5
Introduce one semantic accent.

### Step 6
Choose typography based on readability and personality.

### Step 7
Use imagery as a primary compositional element.

### Step 8
Build interactions with explicit states.

### Step 9
Add motion only where it communicates continuity or creates meaningful delight.

### Step 10
Test accessibility and responsive behavior.

### Step 11
Perform a noise reduction pass.

### Step 12
Perform a final craft pass.

---

# 112. "Never" Rules

Never:

- use animation without a reason
- use color without semantic purpose
- rely on hover for essential functionality
- hide labels for unfamiliar actions
- remove keyboard focus
- use color as the only status signal
- make tiny touch targets
- use huge shadows by default
- put glass on every component
- use random icon styles
- let decorative elements compete with content
- ship without mobile testing
- ship without reduced-motion behavior
- assume desktop layout can simply shrink
- add a feature because the page feels empty
- use "Apple-like" as an excuse to ignore product identity

---

# 113. "Always" Rules

Always:

- design hierarchy first
- use semantic tokens
- preserve accessibility
- make important interactions immediately responsive
- test actual devices
- test intermediate widths
- maintain one visual language
- keep motion purposeful
- use whitespace intentionally
- make the content the hero
- review every component state
- remove unnecessary complexity
- validate the emotional goal

---

# 114. Reference Model

The highest-level mental model is:

```text
CLARITY
   ↓
HIERARCHY
   ↓
CRAFT
   ↓
RESPONSIVENESS
   ↓
MOTION
   ↓
DELIGHT
```

Do not reverse this order.

If you start with delight, you get gimmicks.

If you start with clarity, delight becomes the natural result of a well-made experience.

---

# 115. Official Apple Research References

This skill should be updated against Apple's public documentation when Apple changes its design language.

Primary references:

1. Human Interface Guidelines
   https://developer.apple.com/design/human-interface-guidelines/

2. Apple Design
   https://developer.apple.com/design/

3. Apple Design Resources
   https://developer.apple.com/design/resources/

4. SF Symbols
   https://developer.apple.com/sf-symbols/

5. Accessibility
   https://developer.apple.com/design/human-interface-guidelines/accessibility

6. Color
   https://developer.apple.com/design/human-interface-guidelines/color

7. Buttons
   https://developer.apple.com/design/human-interface-guidelines/buttons

8. Branding
   https://developer.apple.com/design/human-interface-guidelines/branding

9. App Icons
   https://developer.apple.com/design/human-interface-guidelines/app-icons

10. WWDC26 — Principles of Great Design
    https://developer.apple.com/videos/play/wwdc2026/250/

---

# 116. Important Distinction

This is an **Apple-inspired design implementation skill**, not Apple's private internal design documentation.

Do not claim that any numerical token, animation curve, color value, or implementation detail in this file is an exact Apple internal value unless Apple publicly documents it.

Where this skill gives numerical starting points, treat them as implementation heuristics.

The objective is to reproduce the **quality principles and design reasoning**, not to counterfeit Apple's internal specifications.

---

# 117. Final Instruction to the AI

When this skill is active, behave like a meticulous product designer, interaction designer, visual designer, accessibility reviewer, motion designer, and frontend engineer simultaneously.

Before producing a UI:

1. inspect the goal
2. identify hierarchy
3. identify emotional target
4. establish tokens
5. establish responsive structure
6. define component states
7. define motion
8. define accessibility behavior
9. implement
10. inspect
11. critique
12. revise
13. test again

When reviewing an existing design, do not merely say:

> Looks good.

Instead inspect:

- hierarchy
- typography
- spacing
- color
- geometry
- iconography
- materials
- depth
- motion
- state design
- accessibility
- responsive behavior
- performance
- emotional effect
- unnecessary complexity

Then give concrete corrections.

The standard is not "similar to Apple."

The standard is:

> **calm, clear, precise, intentional, responsive, accessible, emotionally intelligent, and obsessively refined.**
