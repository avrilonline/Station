---
name: Design Standard
version: 2.0.0
updated: 2026-10-04
supersedes: 1.1.0
rule-id-pattern: '^(PRN|FND|CTX|LAY|NAV|CMP|ADP|VAL)-\d{2}$'
prefixes:
  PRN: Principles
  FND: Foundations
  CTX: Context
  LAY: Layout
  NAV: Navigation
  CMP: Components
  ADP: Adaptation
  VAL: Validation
levels: [MUST, SHOULD, MAY]
scopes:
  system: the design system satisfies it once, for every product built on it
  view: each screen or page satisfies it
  both: the system makes it possible; each view does it
  review: the reviewer satisfies it; not part of a conformance statement
precedence: [accessibility, reachability, clarity, consistency, content-budget, expression]
decision-order: [view-type, content-types, content-budget, disclosure, user-job, pattern, components, adaptation, validation]
user-jobs: [compare, scan, sequence, find, drill-in]
disclosure-levels: [glance, scan, full-detail]
view-types: [landing, dashboard, docs, wizard, canvas, panel]
content-types: {A: narrative, B: data, C: media, D: structured-record, E: temporal, F: status, G: navigational, H: input, I: proof}
colour-families: [neutral, blue, sky, cyan, teal, emerald, green, lime, yellow, amber, orange, red, pink, purple, violet, indigo]
test-widths: [320, 390, 600, 768, 1024, 1280, 1440, 1920]
retired-ids: [ADP-24, ADP-25]
---

# Design Standard

One set of rules for any product screen and any design system. It is framework-agnostic, content-agnostic and system-agnostic, and it is written so a designer, an engineer, a reviewer and an AI agent reach the same answer.

The standard says **what must be true**. A design system decides **how**, with its own values. The two stay independent: the standard names no system, and a system can be read without the standard. They connect through a separate conformance statement (0.5).

## At a glance

Twelve sentences for anyone who will not read the rules.

1. **One job per screen.** If something does not help with that job, it moves.
2. **The content decides the layout.** Tables compare, timelines order, cards show a few rich items.
3. **Structure before decoration.** With colour and imagery removed, the screen still reads.
4. **One main action, one focal point.** Each screen has one thing it most wants you to do; each section has one place the eye lands.
5. **Show less, keep everything reachable.** Hiding is fine. Losing is not.
6. **Write it once.** Labels and menus are authored in one place and shown everywhere from there.
7. **Respond to the space, not the device.** A half-width window and a phone are both just narrow, and both are designed.
8. **Keep people's place.** Resizing or going back never loses scroll, filters, selection or typing.
9. **Never one signal alone.** Colour comes with text or an icon; hover has a tap equivalent.
10. **Colour means something.** It marks the main action, status and categories. It is never decoration and never absent by default.
11. **Short, calm chrome.** One-word actions, compact navigation, true circles, no stray borders.
12. **Fix the system, not the page.** If it looks awkward, generic, crowded or boxed, fix the component that caused it.

When rules conflict, the higher one wins: **accessibility → reachability → clarity → consistency → content budget → expression**.

## Contents

0. [How to use](#0-how-to-use)
1. [Principles](#1-principles--prn) · `PRN`
2. [Foundations](#2-foundations--fnd) · `FND` · type, space, colour, visual language, states, accessibility, motion, tokens
3. [Context](#3-context--ctx) · `CTX` · view types, content types, content budget, disclosure
4. [Layout](#4-layout--lay) · `LAY` · frame, grid, composition, markers, patterns
5. [Navigation](#5-navigation--nav) · `NAV` · taxonomy, wide, page context, narrow, search, footer
6. [Components](#6-components--cmp) · `CMP` · actions, forms, cards, tables, layers, feedback, canvas
7. [Adaptation](#7-adaptation--adp) · `ADP` · containers, thresholds, narrow layouts, truncation, input, state
8. [Validation](#8-validation--val) · `VAL` · audits, final pass, anti-patterns, report format
9. [Changes in 2.0](#9-changes-in-20)

---

## 0. How to use

### 0.1 Anatomy of a rule

> **NAV-10 · Active state follows the route** `MUST · both`
> Active state MUST match by route pattern, not exact path.

| Part | Meaning |
|---|---|
| `NAV-10` | Stable ID. It is cited in reviews and never reused. Numbers are permanent, so they are not always in reading order. |
| *Active state follows the route* | A plain title. Reading the titles alone gives the gist. |
| `MUST` | The strongest level the rule contains. The modal verbs in the sentence are normative; a SHOULD inside a MUST rule softens only that sentence. |
| `both` | Scope: who satisfies it (0.3). |

A rule is defined once and referenced everywhere else by ID. When a rule and an example disagree, the rule wins.

### 0.2 Levels

| Keyword | Meaning | In review |
|---|---|---|
| **MUST** / **MUST NOT** | Required | Violation = **defect** |
| **SHOULD** / **SHOULD NOT** | Strong default | Unrecorded deviation = **deviation** |
| **MAY** | Permitted, not expected | Never a finding |

### 0.3 Scopes

| Scope | Who satisfies it | Example |
|---|---|---|
| `system` | The design system, once | FND-21: every token pair meets contrast |
| `view` | Every screen built with a system | CTX-02: the screen has one job |
| `both` | The system provides it; the view uses it | NAV-10: the system supplies route matching; the view configures it |
| `review` | Whoever runs an audit | VAL-01: cite a rule for every finding |

### 0.4 Defaults

Values to use when a design system does not define its own. A system MAY change a value; it keeps the relationship. A system that changes one states its value and reason.

| Measure | Default |
|---|---|
| Hit area, any interactive element | ≥ 44 × 44 px |
| Icon-only control | True circle, 44 px |
| Body text | 16–18 px, line height 1.5–1.7, 60–75 characters per line |
| Text levels per view | 3–5 |
| Space scale | 4 · 8 · 12 · 16 · 24 · 32 · 48 · 64 · 96 px |
| Gap between groups | ≥ 2 × the gap within a group |
| Page gutter | 16 (< 600 px) · 24 (600–1023 px) · 32 (≥ 1024 px) |
| Section spacing | One narrow step (40–48 px) and one wide step (64–96 px) |
| Wide navigation | 56 px tall; brand mark ≤ 28 px; ≤ 7 destinations |
| Hero | Headline ≤ 2 lines at 390 px and above, ≤ 3 at 320 px; one supporting sentence ≤ 2 lines; ≤ 2 actions |
| Visible filters | ≤ 3, then "More" |
| Persistent canvas tools | ≤ 7 |
| Motion | 150–200 ms state · 200–300 ms layout |
| Loading indicator delay | 300 ms |
| Contrast | 4.5:1 text · 3:1 large text, boundaries, meaningful graphics |
| Test widths | 320 · 390 · 600 · 768 · 1024 · 1280 · 1440 · 1920, plus a 360 px panel in a wide window |

### 0.5 Conformance statement

A design system conforms by publishing a **conformance statement**: a separate, machine-readable file that names the system and its version, names this standard and its exact version, and lists every `system` and `both` rule with one outcome. `view` and `review` rules are not listed.

| Outcome | Meaning |
|---|---|
| **Met** | The system satisfies the rule. Name the token, component or mechanism. |
| **Deviation** | A SHOULD the system does not follow, with its reason (PRN-13). |
| **Not applicable** | The rule's subject does not exist in the system, with the reason. |
| **Delegated** | A `both` rule the system enables and each view configures. Name the hook. |

An unmet MUST cannot be listed as a deviation (VAL-05). The statement lives beside the system, not inside it, so neither document needs the other.

### 0.6 For agents and reviewers

1. Follow the decision order (PRN-01).
2. Cite rule IDs: *"per NAV-10, active state matches by route pattern"*. Never present a rule as opinion.
3. When rules conflict, apply precedence (PRN-12) and say which rule won.
4. Record SHOULD deviations where they happen (PRN-13).
5. Run the final pass (8.3) before calling anything done.
6. Report in the 8.6 format. A finding without a rule ID is not a finding (VAL-04).

### 0.7 Vocabulary

| Term | Meaning |
|---|---|
| **View** | A screen or page with one job. |
| **View type** | A kind of view with a stated job, content budget and disclosure level (3.1). |
| **Content type** | One of nine recurring kinds of content (A–I, 3.2). |
| **Content budget** | How much content a view type carries per screen-height, step or heading. Not spacing. |
| **Frame** | The one maximum width and gutter shared by navigation, page content and footer. |
| **Container** | The box a component is actually given, as opposed to the viewport. |
| **Wide / narrow** | Representations chosen by container width. Never "desktop / mobile". |
| **Threshold** | A container width at which a component changes representation. |
| **Disclosure level** | Glance (L1), scan (L2), full detail (L3). |
| **Navigation group** | One of the three parts of global navigation: identity, wayfinding, utility. |
| **Hub** | The page a navigation group routes to, introducing its children. |
| **Re-present** | Show the same source in a different container. The opposite of re-author. |
| **Emphasis treatment** | The one visual treatment reserved for the primary action. |
| **Colour family** | A named hue ramp (Blue, Teal, …) from the shared vocabulary. |
| **Artwork** | Supporting graphics that explain an idea. Never interface controls. |
| **Token** | A named design value: colour, size, duration. |

---

## 1. Principles · PRN

### Decision order

```
1 VIEW TYPE → 2 CONTENT TYPES → 3 CONTENT BUDGET → 4 DISCLOSURE → 5 USER JOB
  3.1           3.2               3.3                3.4            3.5
→ 6 PATTERN → 7 COMPONENTS → 8 ADAPTATION → 9 VALIDATION
  4.8         5, 6            7               8
```

**PRN-01 · Decide in order** `MUST · view`
Design decisions MUST follow the decision order. A pattern chosen before the view type and content types are named is provisional and MUST be re-checked against them.

### The principles

**PRN-02 · Job before content** `MUST · view`
Every view MUST have one nameable job. Content that does not serve it MUST NOT be on the view.

**PRN-03 · Content shape decides the pattern** `MUST · view`
Content shape and user task MUST determine the layout pattern. Preference, novelty and "what fits the space" MUST NOT.

**PRN-04 · Structure carries hierarchy** `MUST · both`
Hierarchy MUST read through size, weight, spacing and position before colour, imagery or decoration is added (CTX-17).

**PRN-05 · One primary thing** `MUST · view`
Each view MUST have exactly one primary message or action. Everything else MUST be visibly secondary through size, weight or colour, not order alone.

**PRN-06 · Show less, reach everything** `MUST · both`
Disclosure and adaptation reduce what is shown, never what is reachable. Content available in one context MUST have a visible path to it in every other context.

**PRN-07 · One source of truth** `MUST · both`
Taxonomy, labels and content MUST be authored once. Other containers re-present the source; they MUST NOT re-author or fork it. Display truncation is allowed only as ADP-31 permits, and never for labels.

**PRN-08 · Container, not device** `MUST · both`
Components MUST respond to the space they are given. Device classes and viewport buckets are not design inputs.

**PRN-09 · State is precious** `MUST · both`
Scroll position, filters, selection, open panels and in-progress input MUST survive disclosure navigation, resizing and device handoff.

**PRN-10 · Redundant signals** `MUST · both`
Meaning MUST NOT depend on one channel. Colour pairs with text or an icon; position with explicit order cues; hover with a persistent trigger.

**PRN-11 · Every element earns its place** `MUST · view`
Every element MUST answer "what would break if I were removed?". Elements with no answer, or that only fill space, are removed. The goal is not more interface; it is that everything left is intentional.

**PRN-18 · Fix the system, not the page** `MUST · both`
A problem that recurs MUST be fixed in the shared component, token or rule. A page MUST NOT override a shared component to make itself look right.

**PRN-19 · Don't rationalise** `MUST · both`
Anything that looks awkward, generic, crowded, stale, over-boxed, monochrome, repetitive or unfinished MUST be fixed, not explained. "It works" is not the bar.

### Precedence

```
1 Accessibility → 2 Reachability → 3 Clarity → 4 Consistency → 5 Content budget → 6 Expression
```

**PRN-12 · Resolve conflicts by precedence** `MUST · both`
Conflicts MUST be resolved by this precedence. A MUST at a lower tier never overrides a MUST at a higher tier; within a tier, MUST beats SHOULD beats MAY.

**PRN-13 · Record every deviation** `MUST · both`
A deviation from a SHOULD MUST be recorded with its reason where it happens: a code comment, design note, review comment or conformance statement.

### When unsure

**PRN-14 · Does it belong?** `MUST · view`
The view's job MUST be stated first. Content that does not advance it MUST move to another view or behind an explicit disclosure.

**PRN-15 · Which pattern?** `MUST · view`
The user's job MUST be named with one of five verbs (*compare, scan, sequence, find, drill in*), each mapping to a row of the pattern matrix (4.8).

**PRN-16 · Is it noise?** `MUST · view`
The balance test (CTX-17) MUST be applied before the view ships.

**PRN-17 · When a rule feels wrong** `MUST · both`
The case is either a recorded SHOULD deviation or a proposed change to this standard. Rules MUST NOT be silently ignored.

---

## 2. Foundations · FND

The material every view is built from. The standard sets constraints; a system chooses the values.

```
TYPE       one display face + one body face (+ one monospace for code and data)
SIZE       one type scale + one space scale, with a stated relation
COLOUR     four jobs: emphasis · status · category · expression
SHAPE      true circles · one radius scale · no side stripes
ELEVATION  flat by default · shadow only when something floats
MOTION     purposeful, brief, interruptible, reducible
TOKENS     every value named, every theme checked
```

### 2.1 Typography

**FND-01 · Readable measure** `MUST · both`
Body text MUST sit within a readable measure of roughly 50–75 characters per line.

**FND-02 · Honest heading levels** `MUST · both`
Heading levels MUST form a strict, skip-free hierarchy. Visual size and semantic level MUST agree.

**FND-03 · Few typefaces** `MUST · system`
A system SHOULD use at most two type families, display and body. A third MUST be monospace, reserved for code or data.

**FND-04 · Aligned figures** `MUST · both`
Numeric data in columns MUST use tabular figures or monospace.

**FND-05 · Plain labels** `MUST · view`
Labels and headings MUST describe their content. Clever or vague wording MUST NOT appear on views meant to be scanned.

**FND-45 · Text is not all equal** `MUST · both`
Every view MUST use 3–5 distinct text levels, each separated from the next by at least two of: size, weight, colour or opacity, spacing.

**FND-46 · Vertical rhythm** `MUST · both`
Space above a heading MUST be larger than space below it. Heading, description, controls and content MUST follow one rhythm from the space scale. Supporting text SHOULD be one sentence and at most two lines.

### 2.2 Spacing

**FND-06 · Declared scales** `MUST · system`
Spacing MUST come from one declared space scale, and type from one declared type scale. The system MUST state how the two relate. Ad-hoc values MUST NOT be introduced to "make it fit".

**FND-07 · Groups read without borders** `MUST · both`
The gap between groups MUST be at least twice the gap within a group, so grouping reads without lines or boxes. A group uses one gap per axis.

**FND-08 · Never shrink to fit** `MUST · both`
Content MUST NOT be shrunk to fit. It is split, condensed by disclosure, or re-presented (7).

**FND-47 · One narrow spacing step** `MUST · system`
A system MUST define one narrow and one wide step for section, page-header, band and footer spacing, once. Narrow containers use the narrow step. Pages MUST NOT set their own narrow paddings.

### 2.3 Hierarchy

**FND-09 · Two hierarchy signals** `MUST · both`
Hierarchy MUST use at least two of size, weight, spacing and position.

**FND-10 · One emphasis treatment** `MUST · both`
A system MUST reserve one emphasis treatment for the primary action. At most one action per view carries it (PRN-05). Current location, selected items and tooltips MUST NOT use it. Checked form controls and progress indicators MAY share its fill when their shape keeps them distinct.

### 2.4 Colour

| Job | Carries | How much |
|---|---|---|
| **Emphasis** | The primary action | One per view (FND-10) |
| **Status** | Success · warning · error · info | Fixed families everywhere |
| **Category** | Sections, tags, projects, people, data series | One family per category, stable across the product |
| **Expression** | Artwork | From an artwork palette, never applied to controls |

Family vocabulary: Neutral · Blue · Sky · Cyan · Teal · Emerald · Green · Lime · Yellow · Amber · Orange · Red · Pink · Purple · Violet · Indigo.

**FND-36 · Colour codes something** `MUST · both`
Every colour in the interface MUST carry one of the four jobs. Decorative multicolour (rainbow strips, tinted sections for variety, coloured icons for flavour) MUST NOT be used.

**FND-37 · Not monochrome by default** `MUST · view`
Where a view shows categories, status, data or artwork, colour MUST carry them. An all-grey view is a deliberate choice for a calm reading surface, never the default.

**FND-38 · Categories keep their colour** `MUST · both`
A category MUST map to one family everywhere it appears: badges, avatars, charts, filters, navigation. The mapping MUST be defined once. A view SHOULD show at most eight category colours at once.

**FND-39 · Status families are reserved** `MUST · system`
Status MUST use fixed families (error Red; warning Amber or Yellow; success Green or Emerald; info Blue or Sky). On a view that shows status, categories MUST NOT use the same families.

**FND-40 · Gradients encode something** `MUST · both`
A gradient MAY encode data (a ramp) or form part of artwork. Gradient buttons, gradient text and gradient-washed sections MUST NOT be used.

### 2.5 Visual language

**FND-11 · One icon set, all meaningful** `MUST · system`
Icons MUST come from one set with one stroke weight and MUST carry meaning. Decorative-only icons MUST NOT be used. Icons MUST NOT be stretched, squashed or boxed in awkward containers.

**FND-12 · Named icons** `MUST · both`
Meaningful icons MUST have a text label or an accessible name.

**FND-44 · True circles** `MUST · system`
Every icon-only control MUST be a true circle: equal width and height, fully rounded, never an oval. Its icon sits at the optical centre.

**FND-13 · Shadow means floating** `MUST · system`
Shadows MUST appear only on elements that float: navigation, menus, popovers, sheets, dialogs, dragged items. Flat cards and sections MUST NOT cast them, including on hover.

**FND-41 · No side stripes** `MUST · system`
An element MUST NOT carry a border, inset shadow or bar on only its start or end edge. That includes cards, callouts, quotes, list items, panels, code lines and current or selected states. Use a wash, a weight change or a full outline.

**FND-42 · Containers earn their place** `MUST · both`
A box, card or tinted surface MUST exist only to show grouping, interactivity or elevation. A card MUST NOT sit inside a card. Group with space, type, alignment and subtle surface shifts first.

**FND-43 · One boundary per element** `MUST · system`
A flat container (card, panel, callout, table, code block) MUST draw its edge one way: a border or a fill change, not both. A floating element MAY add a shadow and a hairline. A divider separates siblings only where spacing fails, never above the first or below the last.

**FND-14 · Imagery tied to content** `MUST · view`
Photography, imagery and artwork MUST be tied to the actual content.

**FND-48 · Artwork explains** `MUST · both`
Artwork MUST state one idea about its subject, built from abstract forms (shapes, lines, geometry). Every shape MUST mean something. Artwork MUST NOT be generic (blobs, meaningless gradients, stock-vector people, glossy 3D icons, particle fields). Its style MUST NOT spread to controls. Text inside artwork MUST meet 4.5:1 and MUST be hidden when the art renders too small to read.

**FND-15 · Reserved media boxes** `MUST · both`
Media MUST reserve its aspect ratio before loading.

### 2.6 States

```
INTERACTION                       CONTENT
default · hover (pointer only)    empty · loading · partial
focus (always visible)            error · success · stale or offline
active · selected · disabled
```

**FND-16 · Visible focus** `MUST · system`
Focus MUST be visible on every focusable element and MUST NOT be removed without an equal or stronger replacement.

**FND-17 · Hover is never the only way** `MUST · both`
Hover MUST NOT be the only way to reveal or trigger anything (ADP-13).

**FND-18 · Disabled explains itself** `SHOULD · both`
Disabled controls SHOULD explain why, inline or on focus, when the reason is not obvious.

**FND-19 · Designed empty, loading and error** `MUST · both`
Every state an element can reach MUST be designed. A blank region or default browser output is a defect.

**FND-20 · Status in more than colour** `MUST · both`
Status MUST be shown by colour **and** text or an icon.

### 2.7 Accessibility

**FND-21 · Contrast** `MUST · system`
Contrast MUST meet WCAG 2.2 AA: normal text ≥ 4.5:1; large text, control boundaries, state indicators and meaningful graphics ≥ 3:1.

**FND-22 · Target size** `MUST · both`
Every interactive target MUST have a hit area of at least 44 × 44 CSS px. The visible box MAY be smaller only when its hit area reaches 44 px without overlapping a neighbour's.

**FND-23 · Keyboard** `MUST · system`
Everything interactive MUST be operable by keyboard alone, in a logical order.

**FND-24 · Text alternatives** `MUST · view`
Meaningful media MUST have a text alternative; decorative media MUST be marked as such.

**FND-25 · Semantics match appearance** `MUST · both`
Semantics MUST match appearance: button-looking things are buttons, headings are headings, lists are lists.

**FND-26 · Reflow** `MUST · both`
Content MUST reflow at 200 % zoom and at narrow widths without sideways scrolling of the page (ADP-04).

### 2.8 Motion

**FND-27 · Motion has a purpose** `MUST · system`
Motion MUST show a state change, a spatial relationship or feedback. Parallax, bounce, scroll-jacking and auto-advancing carousels MUST NOT be used unless the content is about motion.

**FND-28 · Brief and interruptible** `MUST · system`
Transitions SHOULD take 150–300 ms. Anything longer MUST be interruptible. Press feedback MUST start within 100 ms.

**FND-29 · Reduced motion** `MUST · system`
Non-essential motion MUST respect the reduced-motion preference, and the still state MUST be the finished state.

**FND-30 · Motion is never the only cue** `MUST · system`
Motion MUST NOT be the only cue for a state change.

### 2.9 Tokens and themes

**FND-31 · Every value is a token** `MUST · system`
Every visual value a component uses MUST resolve to a named token, named by role, never by appearance or page.

**FND-32 · Machine-readable publication** `MUST · system`
A system MUST publish its tokens machine-readably. It SHOULD use an open format and pass that format's validator with zero errors. Values the format cannot carry MUST still be machine-readable, never only in prose.

**FND-33 · Every theme passes on its own** `MUST · system`
Each theme MUST meet FND-21 independently, with its own measured values.

**FND-34 · Fills have foregrounds** `MUST · system`
Every colour role used as a fill behind text or icons MUST have a matching foreground role.

**FND-35 · Forced colours** `MUST · system`
Under forced-colours modes, every control, boundary, focus indicator and state MUST stay perceivable.

---

## 3. Context · CTX

What belongs on a view and how much of it.

### 3.1 View types

| View type | Job | Content budget | Default disclosure |
|---|---|---|---|
| **Landing** | Persuade, then convert | One message per screen-height | L1 |
| **Dashboard** | Monitor, then act | Most-checked data first; rare actions in menus | L1 → L2 |
| **Docs** | Explain | One concept per heading; examples after their rule | L3 |
| **Wizard** | Complete one task | One decision per step; no side content | L2 |
| **Canvas** | Make or edit one artefact | The artefact first; tools when needed | L2 |
| **Panel** | Show one slice in a narrow region | One list or one record | L1 |
| **Form** (inside any view) | Collect | One decision per row | L2 |

**CTX-01 · Name the view type first** `MUST · view`
The view type MUST be named before content is added.

**CTX-02 · One job per view** `MUST · view`
A view MUST have one job. A view doing two SHOULD be split.

**CTX-03 · New view types state their terms** `MUST · both`
Systems and products MAY define new view types. Each MUST state its job, content budget and default disclosure.

**CTX-18 · Dashboards are for monitoring** `MUST · view`
A grid of metric tiles MUST be used only when the user's job is to watch numbers and act on them. Otherwise the view uses a composition shaped by its content (LAY-34).

### 3.2 Content types

| ID | Type | Contains | Needs |
|---|---|---|---|
| **A** | Narrative | Paragraphs, long-form copy | Measure, heading levels, one idea per paragraph |
| **B** | Data | Numbers, metrics, financials | Tabular figures; tables for precision, charts for pattern |
| **C** | Media | Photo, video, illustration, audio | Reserved ratio, text alternative, a real reason |
| **D** | Structured record | Entities with fields | A declared disclosure level |
| **E** | Temporal | Steps, history, timelines | Explicit order cues |
| **F** | Status | Success, error, warning, empty, loading | Colour + icon + text; designed states |
| **G** | Navigational | Menus, breadcrumbs, tabs, search | Current location always shown |
| **H** | Input | Fields, selectors, prompts, uploads | 6.3 |
| **I** | Proof | Testimonials, reviews, logos | Named source, real number |

**CTX-04 · List the content types** `MUST · view`
The content types present MUST be listed before layout. If they cannot be named, return to CTX-01.

**CTX-05 · Two to four types** `SHOULD · view`
A view SHOULD mix two to four content types.

**CTX-06 · Each type gets its needs** `MUST · both`
Each content type MUST receive at least the treatment in its "Needs" column.

### 3.3 Content budget

**CTX-07 · Budget matches the job** `MUST · view`
The amount of content MUST match the view type's budget. A section with three unrelated ideas MUST be split, not shrunk.

**CTX-08 · Frequency decides placement** `SHOULD · view`
On task views, the most-checked information SHOULD sit where the eye lands first.

**CTX-09 · One concept per heading** `MUST · view`
On reading views, each heading SHOULD own one concept, and examples MUST sit next to the rule they illustrate.

### 3.4 Progressive disclosure

| Level | Answers | Shows | A record, for example |
|---|---|---|---|
| **L1 Glance** | What is it? Is it for me? | Title, summary, key status | Card in a list |
| **L2 Scan** | Should I act? | A few details, the primary action | Preview pane |
| **L3 Full** | Everything, on request | Every field, history, edge cases | Detail page |

**CTX-10 · Declare the level** `MUST · view`
Every view MUST declare its disclosure level. L3 detail MUST NOT sit in an L1 list "just in case".

**CTX-11 · One clear trigger deeper** `MUST · both`
Advancing a level MUST take one visible trigger and MUST NOT happen by accident.

**CTX-12 · Going deeper keeps your place** `MUST · both`
Returning from a deeper level MUST restore scroll, filters and selection.

**CTX-13 · A path deeper always exists** `MUST · view`
A visible path deeper MUST always exist.

**CTX-14 · Advanced on request** `MUST · view`
The primary action MUST be visible at once. Secondary options appear in context. Bulk actions, raw configuration and danger zones MUST sit behind one explicit trigger.

### 3.5 The user's job

```
1 Name the view type ............................ CTX-01
2 Name the job in one sentence .................. CTX-02
3 List the content types ........................ CTX-04
4 Set the content budget ........................ CTX-07
5 Declare the disclosure level .................. CTX-10
6 Name the user's job with ONE verb ............. CTX-15
7 Map type + verb to a pattern .................. 4.8
```

**CTX-15 · One verb** `MUST · view`
The user's job MUST be named with one verb before a pattern is chosen: *compare*, *scan*, *sequence*, *find*, *drill in*.

### 3.6 Richness without noise

| Richness | Noise |
|---|---|
| Artwork that explains the subject | Blobs, gradient washes, stock vectors |
| Category and status colour | Grey everywhere, or rainbow decoration |
| Captioned charts | Decorative icons |
| Whitespace as a deliberate pause | Dead space, or cramming |
| Composition shaped by the content | Identical card rows |

**CTX-16 · Richness from the left column** `MUST · both`
Richness MUST come from the left column. Right-column items are defects under the rules they break.

**CTX-17 · Balance test** `MUST · view`
With every decorative element removed, the view MUST still communicate its hierarchy through structure and space alone.

---

## 4. Layout · LAY

```
frame (max width + gutter) ▸ region ▸ section (one idea) ▸ component
```

### 4.1 The frame

**LAY-24 · One frame** `MUST · both`
Navigation, every page container and the footer MUST share one frame: the same maximum width and the same gutter. The identity group's outer edge MUST align with the content's start edge, the utility group's with the content's end edge, and the footer with both.

**LAY-25 · Narrow columns sit in the frame** `MUST · system`
A column narrower than the frame (a reading column, a form) MUST sit inside it, aligned by one system-wide rule. A page MUST NOT create its own narrower frame with different edges.

**LAY-01 · Capped content** `MUST · both`
Reading text MUST cap at the measure (FND-01). A wider frame adds margin or room for wide content, never longer lines.

**LAY-02 · Shallow nesting** `MUST · both`
Nesting MUST stay shallow: frame → region → section → component.

**LAY-03 · One idea per section** `MUST · view`
A section MUST contain one idea.

**LAY-04 · Wide content scrolls itself** `MUST · both`
Tables, code and diagrams MUST scroll inside their own container. The page MUST NOT scroll sideways.

### 4.2 Grid

**LAY-05 · Gutters from the scale** `MUST · system`
Layouts MUST use gutters from the space scale.

**LAY-06 · Columns from content** `MUST · both`
Column counts MUST derive from content (a minimum cell width, or the measure), not from a fixed 12-column convention.

**LAY-07 · Fluid grids** `MUST · both`
Grids MUST be fluid. Fixed widths MAY be used only for fixed-size content.

### 4.3 Focal point and alignment

**LAY-10 · Primary lands first** `MUST · view`
The primary action or message MUST sit where the reading direction lands first and MUST be the heaviest element there.

**LAY-15 · Structure at a glance** `MUST · view`
Blurred until text is unreadable, the view MUST still show its regions and its primary action. Every section MUST have one focal point and one reading order.

**LAY-08 · Proximity first** `MUST · both`
Related items MUST be grouped by proximity first.

**LAY-09 · Real gaps between groups** `MUST · both`
Independent groups MUST have real negative space between them. Items MUST NOT be spread evenly across the full width.

**LAY-11 · Shared alignment edges** `MUST · both`
Elements in one region MUST share alignment edges. Mixed alignment is a defect unless the centred element is a single headline or a self-contained empty state.

**LAY-12 · Start-aligned text** `MUST · both`
Text MUST be start-aligned, except short display headlines, empty states and numeric columns.

**LAY-13 · Numbers align right** `MUST · both`
Numeric columns MUST be right-aligned with tabular figures.

**LAY-14 · Labels align with what they name** `MUST · both`
Labels MUST align with what they name.

**LAY-16 · Headings match containers** `MUST · view`
There MUST be one h1 per page and one h2 per region or top-level section.

**LAY-17 · Secondary content is lighter** `MUST · view`
Asides and metadata MUST be visibly lighter than primary content and MUST NOT interrupt the reading path.

### 4.4 Hero and page header

A hero holds at most: an optional eyebrow or section marker; a headline; one supporting sentence; up to two actions, one of them primary; one visual (see 0.4 for sizes).

**LAY-26 · The hero is not a summary** `MUST · view`
A hero MUST hold nothing beyond that list: no metric rows, logo walls, feature lists, stacked badges or multiple paragraphs.

**LAY-27 · The next section peeks** `MUST · view`
The top of the next section MUST be visible in the first screen at every test width.

**LAY-28 · The strongest content comes next** `MUST · view`
Directly beneath the hero MUST sit the strongest content: the core idea, the product in use, or the main task. A generic row of metric tiles is not that.

```
Title                                          [Secondary] [Primary]
One-line description
[Search .....................] [Filter] [Filter] [Filter] [More ▾]  [View]
```

**LAY-29 · Title and actions share a row** `MUST · both`
On working views (dashboards, lists, records, editors), the page title and its actions MUST share one row: title at the start, actions at the end, vertically centred on the title.

**LAY-30 · One toolbar row** `MUST · both`
Search, filters and view controls MUST sit in one row below the title, on the same edges. At most three filters are visible; the rest sit behind "More", which shows the active count.

**LAY-31 · No orphaned controls** `MUST · view`
A control MUST NOT sit alone in its own row, far from what it affects, or apart from its label.

### 4.5 Balance

**LAY-32 · No dead space, no cramming** `MUST · view`
An empty area inside a region MUST NOT exceed the section spacing unless it is a deliberate pause, and no gap may be smaller than the space scale's smallest step. Margin beside a capped reading column is not dead space. Asymmetry MUST be deliberate, with one side clearly dominant.

**LAY-33 · Balanced columns** `MUST · view`
A column in a multi-column layout MUST NOT be more than twice the height of its neighbour. A grid SHOULD NOT end with one stranded item when another column count avoids it.

**LAY-34 · Composition fits the content** `SHOULD · view`
A composition shaped by the content (a lead item, a featured record, a worked example, a sequence) SHOULD be preferred over a uniform grid of identical cards.

### 4.6 Section markers

```
┌───┐
│ 3 │  Section title
└───┘
```

**LAY-35 · One marker style** `MUST · system`
Every chapter or section number MUST appear the same way everywhere: a plain numeral inside a light 1px border, muted, unfilled, smaller than the heading it precedes. The section sign MUST NOT be printed.

**LAY-36 · No decorative numbering** `MUST · system`
Numbers MUST NOT appear in badges, filled shapes, gradients or oversized outlined numerals. Legacy treatments MUST be replaced, not kept beside the new one.

### 4.7 Patterns

| Pattern | For |
|---|---|
| **Single column** | Reading, forms, wizards |
| **Sidebar + main** | Docs, settings, admin |
| **Card grid** | Few records, rich detail |
| **Table** | Many rows, comparison |
| **Master-detail** | List beside record |
| **Timeline / stepper** | Temporal content |
| **Board** | Status across stages |
| **Hub** | The page behind a navigation group: one entry per child, same copy as the navigation |

**LAY-18 · Patterns from the matrix** `MUST · view`
Patterns MUST be chosen from the matrix (4.8) by content type and job.

**LAY-19 · Verb before pattern** `MUST · view`
The user's job MUST be named with one verb before a pattern is chosen.

**LAY-20 · Tables for exact values** `MUST · both`
If users must cite an exact number, the view MUST provide a visible table, alone or beside the chart.

**LAY-21 · Same content, same pattern** `MUST · view`
The same content type MUST NOT use different patterns in nearby views without a stated reason.

**LAY-22 · Every chart says what it shows** `MUST · both`
Every non-trivial chart MUST carry a one-line caption stating its finding.

### 4.8 Pattern matrix

| Type · shape | Job | Use | Avoid |
|---|---|---|---|
| **B** many rows, few fields | compare | Table | Cards |
| **B** quantity across categories | compare | Bar / column | Pie > 5 slices |
| **B** part-to-whole, ≤ 5 parts | scan | Donut or stacked bar | Many-slice pie |
| **B** trend over time | scan | Line | Bar, beyond ~12 points |
| **B** exact values | find | Table | Any chart alone |
| **D** few items, rich detail | scan, drill in | Card grid | Table |
| **D** hierarchical | find, drill in | Tree, nested list | Flat list |
| **A** few fields, low compare | scan | List | Table |
| **E** ordered steps | sequence | Timeline / stepper | Card grid |
| **E** status across stages | scan | Board | Table |

**LAY-23 · Matrix levels** `MUST · view`
"Use" is a SHOULD and "Avoid" a SHOULD NOT. Deviations MUST be recorded.

---

## 5. Navigation · NAV

One navigation system across pages, docs, search and editors, at every width. Compact, quiet, and never competing with the content.

### 5.1 The taxonomy

**NAV-28 · One source** `MUST · both`
Destinations, labels, order, icons, descriptors and route patterns MUST be defined once, as data, and read by every representation: wide row, rail, menu sheet, footer and hubs.

**NAV-29 · Short, few, unbroken** `MUST · both`
There MUST be at most seven top-level destinations. Labels SHOULD be one word, are never more than two, and MUST NOT wrap or truncate. When labels do not fit, the representation changes (NAV-38).

**NAV-05 · Groups by taxonomy** `MUST · view`
Groups MUST be formed by real categories, never by overflow. "More" MUST NOT be a bucket for unrelated items.

**NAV-07 · Groups have a hub** `MUST · view`
Every group MUST route to a hub page that lists its children. A dropdown MAY be added for a short group; the label still routes to the hub.

**NAV-06 · Children describe themselves** `MUST · both`
Every child MUST have an icon, a label and a one-line descriptor, the same copy as on its hub.

**NAV-08 · One level deep** `SHOULD · view`
Groups SHOULD be one level deep.

**NAV-09 · Always show where you are** `MUST · both`
The current location MUST always be indicated.

**NAV-10 · Active state follows the route** `MUST · both`
Active state MUST match by route pattern, not exact path: on `/reports/q3/export`, `Reports` is active because `/reports/**` matches.

**NAV-11 · Two active signals** `MUST · system`
Active state MUST use two signals, such as a wash plus a weight change, and MUST NOT rely on colour alone or a side stripe.

### 5.2 Wide navigation

```
( ◉ Brand )        ( Overview  Docs  Pricing  Blog )        ( ⌕  ◐  ● )
 identity                     wayfinding                        utility
```

**NAV-01 · Three groups, one row** `MUST · both`
Wide navigation MUST be one row of three groups (identity, wayfinding, utility) of equal height, sharing surface, radius and elevation. Groups MUST NOT be merged, and there MUST NOT be a fourth group or a second row.

**NAV-30 · Compact and quiet** `MUST · system`
The row MUST sit in the frame (LAY-24) and MUST be compact (see 0.4). It MUST NOT be a full-width opaque slab, use heavy type, or carry an oversized logo.

**NAV-02 · Brand goes home** `MUST · view`
The identity group MUST hold the brand, routing to the product root.

**NAV-03 · Wayfinding holds only taxonomy** `MUST · view`
The wayfinding group MUST hold the top-level destinations and nothing else.

**NAV-31 · Wayfinding is centred** `MUST · both`
The wayfinding group MUST be centred on the frame however wide the other groups are.

**NAV-04 · Clusters, not a spread** `MUST · both`
Each group MUST be a cluster with real space around it (LAY-09).

**NAV-12 · Stateless utilities** `MUST · view`
Utilities with no sub-navigation MUST be stateless buttons.

**NAV-15 · One small utility cluster** `MUST · both`
The utility group MUST read as one cluster of at most three controls: search, one grouped menu (account, or preferences when there are no accounts), and at most one other direct action.

**NAV-13 · One account menu** `MUST · view`
When the product has signed-in users, the utility group MUST hold exactly one account menu, with preferences inside it. Signed out, it becomes a one-word "Sign in". A product without accounts records this rule as not applicable.

**NAV-14 · Direct actions stand alone** `MUST · view`
A direct action MUST NOT be merged into the account menu.

**NAV-32 · The row stays put** `MUST · system`
The row MUST NOT hide, shrink or change layout on scroll. Only its shadow MAY deepen.

**NAV-33 · No menu button at wide** `MUST · view`
While the wide row fits, wayfinding MUST stay visible. A menu button in its place is a defect.

**NAV-26 · Rail for tool-heavy apps** `MUST · both`
Apps and canvases with many tools MAY use a start-edge rail of true circles instead of the wayfinding group. It MUST render the same taxonomy, and only one wayfinding representation shows at a time.

### 5.3 Page context

```
(←)  Q3 report  · ✓ Saved                              [Share]  [Publish]
```

**NAV-34 · Back is a floating circle** `MUST · both`
On any view with a parent, back MUST be an icon-only, floating, true-circle button at the start edge. Its accessible name says where it goes ("Back to Projects"). It returns to the previous view in the same flow with its state restored, or to the logical parent when entered directly. Back MUST NOT be a text link.

**NAV-35 · Title and save state stay small** `MUST · both`
The page name MUST appear once at a time, and on one line wherever it sits in compact chrome (a context bar, a narrow top bar). Save state MUST be one compact status beside it: an icon plus one word (Saved, Saving, Unsaved, Offline, Failed), announced politely. Routine saves MUST NOT raise a banner or toast; only a failure becomes prominent, with a one-word action.

**NAV-36 · Focus mode keeps the exits** `MUST · both`
An editor, canvas or wizard MAY replace the wide row with a context bar (back, title, save state, actions). Search and every destination MUST stay reachable from it.

**NAV-37 · Breadcrumbs only when deep** `MUST · view`
Breadcrumbs MUST appear only three levels deep or more, collapse middle levels into a menu, and never wrap.

### 5.4 Narrow navigation

```
TOP     ( ◉ )                                          ( ⌕  ◐ )
        brand mark                                     utility

BOTTOM  ( ≡ )                                             ( ↑ )
        menu                              page action, or a useful default
```

**NAV-38 · Switch by measured fit** `MUST · both`
The narrow representation MUST take over when the wide row no longer fits its three groups on one line at full label length, measured on the navigation's own container. Never by device.

**NAV-48 · One brand mark** `MUST · system`
The brand mark MUST be the same asset at every width. At narrow widths it shows alone, with the name as its accessible name.

**NAV-39 · Utilities stay at the top** `MUST · both`
Search and preferences MUST stay together at the top end at narrow widths. Search MUST NOT move to the bottom or into a menu only.

**NAV-40 · Two circles, never a pill** `MUST · both`
The bottom of a narrow view MUST hold a floating circular menu button at the start and a floating circular action at the end, of the same diameter and elevation, symmetrically placed. A single floating pill of destination links MUST NOT be the narrow navigation. A view with nothing useful for the end circle MAY show the menu circle alone.

**NAV-41 · Centre only when useful** `MUST · both`
A component MAY sit between the two circles only when it genuinely serves the current task: playback, canvas tools, wizard progress, or a selection count. It MUST be one line, as tall as the circles, and MUST NOT be the only path to anything.

**NAV-42 · The menu sheet** `MUST · both`
The menu button MUST open a sheet listing every destination in the same order, with the same labels and one-line descriptors (truncating, never wrapping), the account and preferences. It opens with the current item visible, traps focus, and closes on Escape, the system back gesture or a close circle.

**NAV-18 · Same taxonomy at narrow** `MUST · both`
Narrow navigation MUST present the same taxonomy, labels and descriptors as wide, without re-authoring, reordering or truncating labels.

**NAV-19 · Sheets, not hover menus** `MUST · system`
Groups at narrow MUST open in the sheet, never on hover.

**NAV-20 · Utilities stay reachable** `MUST · both`
Account and preferences MUST stay reachable at narrow widths.

**NAV-27 · Within thumb reach** `SHOULD · both`
Narrow primary controls SHOULD sit at the bottom edge.

**NAV-45 · Content clears the chrome** `MUST · both`
Content MUST reserve space so nothing hides behind floating navigation. Anchors and focused elements MUST land below sticky chrome. Bottom controls MUST step aside while the on-screen keyboard is open.

### 5.5 Search and preferences

**NAV-43 · Search is one tap from the top** `MUST · both`
Search MUST be reachable from the top at every width, with a keyboard shortcut shown in its tooltip. It opens a layer that shows recent items before typing, announces result counts, and names the query when nothing matches.

**NAV-44 · Preferences are compact** `MUST · both`
Theme MUST be a compact preference: a three-option control (Light, Dark, Auto) inside the grouped menu, or a circular icon showing the current mode that opens it. Other preferences MUST join it rather than add controls. A large toggle switch in the navigation is a defect.

### 5.6 Persistent controls

**NAV-16 · Persistent controls outlive pages** `MUST · both`
Page-independent controls (playback, a call, an upload, sync) MUST live in their own floating element and keep their state across navigation, menus and overlays.

**NAV-17 · One home per width** `MUST · both`
A persistent control MUST sit at the bottom end at wide widths, and between the narrow circles (NAV-41) at narrow widths.

**NAV-21 · Never in the menu** `MUST · both`
Persistent controls MUST NOT be placed inside the menu sheet.

### 5.7 In-page navigation

**NAV-46 · Tabs, contents and pagers** `MUST · both`
Tabs MUST switch siblings in one view, use one-word labels, mark the current tab with two signals, and scroll rather than wrap. A page with four or more sections MUST offer a contents list (beside the content when wide, a disclosure at the top when narrow). Previous and next pagers MUST be links with a one-line, truncating title.

### 5.8 Footer

```
One-line closing statement.                                        (↑)
Product        Resources        Company
◉ © 2026 Brand   [v2.4.0]  [● Operational]                Terms · Privacy
```

**NAV-25 · A deliberate conclusion** `MUST · view`
The footer MUST be compact, with up to three bands: an optional closing line with a circular "Top" button, link columns, and a meta line ending in the legal links.

**NAV-47 · Metadata, not paragraphs** `MUST · both`
Version, status and environment MUST appear as small badges or inline labels. The footer MUST NOT hold paragraphs, or a newsletter or marketing block unless that is the page's job.

**NAV-22 · Columns, never a list** `MUST · both`
Link columns MUST appear only when there are destinations beyond the top level. When they appear, there MUST be at least two at every width, never one stacked list. Link labels MUST truncate rather than wrap.

**NAV-23 · Footer uses the same taxonomy** `MUST · view`
Footer columns MUST use the taxonomy's groups.

**NAV-24 · No duplicate link lists** `MUST · view`
Apart from the taxonomy itself, the footer MUST NOT repeat a list that exists elsewhere, such as social links already in the utility group.

---

## 6. Components · CMP

A component is a contract:

```
INPUT      content of one declared type
CONTAINER  adapts to the box it is given
STATES     every interaction and content state
ACTION     at most one primary
ESCAPE     a way to dismiss, undo or go back
```

### 6.1 General

**CMP-01 · Declared content type** `MUST · system`
A component MUST declare which content types it presents.

**CMP-02 · Adapts to its container** `MUST · system`
A component MUST adapt to its own container.

**CMP-03 · Every state designed** `MUST · system`
A component MUST design every state it can reach.

**CMP-04 · One primary action** `MUST · both`
A component MUST have at most one primary action.

**CMP-05 · Compose, don't copy** `MUST · system`
Composition MUST nest declared components, not copy markup.

**CMP-06 · Variants need a job** `MUST · system`
A variant MUST be justified by a different job, not a different page.

### 6.2 Actions and labels

| Instead of | Use |
|---|---|
| Create workspace | Create |
| Save changes | Save |
| Open project | Open |
| Submit · OK · Yes | The specific verb |

**CMP-08 · One-word actions** `MUST · both`
Every top-level action label (page header, toolbar, card, dialog, form footer, empty state, floating action) MUST be one verb naming the outcome. The object comes from context. A fixed phrasal verb with no one-word equivalent ("Sign in", "Log out") counts as one word.

**CMP-37 · Labels never wrap** `MUST · both`
Action labels MUST stay on one line at every width. If a label does not fit, the layout gives it room, moves it to overflow, or shows an icon-only circle for a universally recognised action. The accessible name MAY add the object ("Delete" → "Delete Q3 report") and MUST begin with the visible word.

**CMP-07 · Three tiers, one primary** `MUST · both`
Actions MUST use at most three tiers: primary (the emphasis treatment), secondary, tertiary. Primary appears once per view.

**CMP-09 · Destructive is distinct** `MUST · both`
Destructive actions MUST be distinct, never primary by default, and confirmable or undoable. A confirmation's title names the object; its button repeats the verb.

**CMP-10 · Named icon buttons** `MUST · both`
Icon-only buttons MUST have an accessible name and a tooltip.

**CMP-38 · Feedback speaks the action's word** `MUST · both`
State changes MUST confirm in the action's own word: Save → Saving… → Saved.

### 6.3 Forms and input

**CMP-39 · One input family** `MUST · system`
Text fields, textareas, selects, comboboxes, dates, search, command and prompt inputs MUST share boundary, radius scale, typeface, padding rhythm, icon size and states, and one height except where content needs more (a growing prompt, code cells). None looks like a browser default.

**CMP-40 · Every layer designed** `MUST · system`
Each input MUST define its label, value, affordance (chevron, icon, clear), supporting text, focus, and validation and error states, using one boundary.

**CMP-11 · Labels stay visible** `MUST · both`
The label MUST always be visible, above the field or stacked inside it, chosen once per system. A placeholder MUST NOT be the only label.

**CMP-12 · One decision per row** `MUST · view`
Each row MUST hold one decision. Related fields MUST be grouped under one heading.

**CMP-13 · Validation helps** `MUST · both`
Validation MUST run on submit and on blur for filled fields, never per keystroke. Errors MUST show colour, icon and text, and say how to fix.

**CMP-14 · Mark the minority** `MUST · both`
Forms MUST mark either required or optional fields, whichever is fewer, and say once which.

**CMP-15 · Input type matches data** `MUST · view`
Free text MUST NOT stand in for a constrained choice.

**CMP-16 · Input survives** `MUST · both`
Forms MUST keep in-progress input across navigation, resizing and errors.

**CMP-17 · Steps, not tabs** `SHOULD · view`
Long forms SHOULD be split into steps rather than tabs.

**CMP-41 · Prompts lead, options follow** `MUST · both`
A generator or command input MUST be one growing field with its key actions inside it. Advanced options MUST sit behind a disclosure, not as a row of selects above it.

### 6.4 Cards

**CMP-18 · One record per card** `MUST · both`
A card MUST present one record at a declared disclosure level.

**CMP-19 · Same fields in a grid** `MUST · view`
Cards in a grid MUST share field set and order.

**CMP-20 · One target per card** `MUST · both`
A card MUST have one primary target.

**CMP-21 · No cards for rows** `MUST · view`
Cards MUST NOT be used for many-row, few-field data.

### 6.5 Tables

**CMP-22 · Real table semantics** `MUST · system`
Tables MUST use real table semantics.

**CMP-23 · Columns by frequency** `MUST · view`
Column order MUST be identifier first, most-compared next, actions last.

**CMP-24 · Sort and filter persist** `MUST · both`
Tables MUST support their job, and sort and filter state MUST persist.

**CMP-25 · Keyboard row actions** `MUST · system`
Row actions MUST be keyboard-reachable and never hover-only.

**CMP-26 · Bulk needs selection mode** `MUST · both`
Bulk actions MUST sit behind an explicit selection mode.

**CMP-27 · Empty tables help** `MUST · both`
Empty tables MUST show a designed empty state with the next action.

### 6.6 Layers

| Layer | Use |
|---|---|
| **Tooltip** | A control's name or shortcut |
| **Popover** | Small, non-blocking detail |
| **Menu** | ≤ 8 actions on one trigger |
| **Drawer** | A secondary task beside the page |
| **Sheet** | Narrow replacement for the above |
| **Dialog** | A decision that blocks the flow |
| **Toast** | Brief confirmation of a finished action |

**CMP-28 · Every layer opens and closes every way** `MUST · system`
Every layer MUST open by pointer, touch and keyboard, dismiss with Escape and an explicit close, and return focus to its trigger.

**CMP-29 · Lightest layer first** `MUST · view`
Dialogs MUST be reserved for decisions that block the flow. Information, settings and long forms use a popover, drawer or page.

**CMP-42 · Native dialogs** `MUST · system`
A dialog MUST use the system's surfaces, radius, type and motion, never a generic box. It has a title naming the decision, an optional line of context, the body, a primary action at the end, a secondary beside it, and a close circle. It is sized to its content, uses one boundary, never opens another dialog, and becomes a bottom sheet at narrow widths.

### 6.7 Feedback

**CMP-30 · Chart captions** `MUST · both`
Every chart MUST carry a one-line caption (LAY-22).

**CMP-31 · Five statuses** `MUST · system`
Status components MUST combine colour, icon and text for success, warning, error, info and in-progress.

**CMP-32 · Toasts are not the only path** `MUST · both`
Toasts MUST be one line, dismissible, and never the only path to an action.

**CMP-43 · Empty states instruct** `MUST · both`
An empty state MUST have an icon or artwork, a title in the user's words, one sentence on what to do, and one action. A "no results" state names the query and offers a way out.

**CMP-44 · Loading shows shape** `MUST · both`
Loading MUST wait 300 ms before showing an indicator, then use a skeleton with the real layout's boxes so nothing shifts. A working control shows a spinner in place of its icon, with its width locked.

**CMP-45 · Errors fit their reach** `MUST · both`
An error MUST appear at the level that failed (field, form, region or page), say what happened and what to do, keep the user's work, and never apologise or blame.

### 6.8 Media, proof, disclosure, canvas

**CMP-33 · Specific proof** `MUST · view`
Proof MUST name a source and a real number.

**CMP-34 · Media earns its place** `MUST · both`
Media MUST reserve aspect ratio, have text alternatives, and exist for a content reason.

**CMP-35 · Announced disclosure** `MUST · system`
Accordions and "show more" MUST have a visible trigger whose state is announced.

**CMP-36 · Tooltips clarify only** `MUST · both`
Tooltips MUST NOT hold information required for a task. A truncated value a task needs MUST also be reachable another way.

**CMP-46 · The canvas stays calm** `MUST · both`
A canvas MUST show the artefact first, with seven or fewer persistent tools floating near the work as part of the environment, not an admin toolbar. Tools for a selection appear beside it. Advanced tools open on request, and shortcuts appear in tooltips and menus.

---

## 7. Adaptation · ADP

People resize windows, snap to half a screen, rotate and fold devices, and hand off between screens. Adaptation re-presents; nothing is lost, nothing is re-authored, and every width is designed.

| Avoid | Use |
|---|---|
| mobile / tablet / desktop tiers | Fluid layouts, no device tiers |
| Device-width breakpoints | Thresholds where content breaks |
| Page-wide media queries for structure | Container queries |
| "Hide on mobile" | Re-flow or condense; nothing vanishes |
| Shrunk desktop | A layout chosen for the width |

### 7.1 Container-driven

**ADP-01 · Respond to the container** `MUST · both`
A component MUST respond to its container, not the window or device class.

**ADP-02 · No device names** `MUST · system`
Device names MUST NOT be design inputs. Capabilities MAY be: input modality, hover, safe areas, reduced motion.

**ADP-03 · Fluid between thresholds** `MUST · both`
Layouts MUST be fluid between thresholds.

**ADP-04 · No sideways page scroll** `MUST · both`
At any width the page MUST NOT scroll sideways.

**ADP-33 · Widths are independent** `MUST · both`
The frame, the reading measure and floating elements MUST each size from their own rules. None stretches because the window did.

### 7.2 Thresholds

**ADP-05 · Thresholds where content breaks** `MUST · system`
A threshold MUST sit where content actually breaks, with its derivation documented beside it.

**ADP-06 · Thresholds are owned** `MUST · system`
A threshold MUST be owned by the component or region whose content breaks. Shared named container thresholds MAY exist if each is derived. Viewport thresholds MAY drive only page-level presentation (fluid type, gutters), never structure.

### 7.3 Narrow is first-class

**ADP-29 · Narrow is designed** `MUST · both`
Every view MUST have a designed layout from 320 px, and inside a 360 px panel of a wide window. Padding, gaps, type steps and hierarchy MUST be re-chosen at each width, not scaled down, and wasteful spacing removed.

| Pattern | Wide | Narrow |
|---|---|---|
| Global navigation | Three groups in one row | Brand + utilities at top; menu and action circles at bottom |
| Sidebar + main | Side by side | Main; sidebar in a sheet |
| Table | Full columns | Stacked label-value rows, or scroll in its container |
| Card grid | n columns | Fewer columns, same cards |
| Toolbar | Actions inline | Primary inline, rest in overflow |
| Filter row | Inline filters | "Filters" button with active count |
| Dialog | Centred | Bottom sheet |

**ADP-07 · Everything reachable at narrow** `MUST · both`
Everything reachable at wide MUST have a reachable equivalent at narrow. Nothing is simply hidden.

**ADP-08 · Same labels at narrow** `MUST · both`
Narrow representations MUST keep the same labels, order and taxonomy.

**ADP-09 · Condense by disclosure** `MUST · both`
Condensing MUST happen through disclosure, not by shrinking type, spacing or targets below their minimums.

**ADP-10 · Primary action never in overflow** `MUST · both`
The primary action MUST stay visible at every width, and MUST NOT appear twice.

**ADP-32 · Don't stack everything** `MUST · view`
At narrow widths, short paired items (two stats, a label and value) MUST stay side by side when they fit.

### 7.4 Wrapping and truncation

**ADP-30 · Controls never wrap** `MUST · both`
Buttons, chips, tabs, segmented controls, navigation labels and single-line labels MUST NOT break across lines. The layout gives them room or changes representation. Headings MAY wrap, balanced, never leaving one word alone on the last line.

**ADP-31 · Truncate with a way back** `MUST · both`
Text that would reflow into uneven stacks MUST truncate instead, by this table, and the full value MUST stay reachable.

| Content | Treatment |
|---|---|
| Single-line labels in rows, descriptors, pager and rail titles, breadcrumbs, footer links | One line, ellipsis at the end |
| Summaries | Clamp to 2–3 lines |
| IDs, paths, hashes | Keep start and end: `a3f9…77c2` |
| Action labels, navigation labels, numbers, page headings | Never truncated |

The full value stays reachable as the accessible name and a tooltip, plus copy or expand when a task needs it.

### 7.5 Input

**ADP-11 · Pointer and touch together** `MUST · both`
Touch and pointer MUST both be assumed possible at once. No interaction or target size is gated to one input type.

**ADP-12 · Touch targets everywhere** `MUST · both`
Targets MUST meet FND-22 in every representation.

**ADP-13 · Hover and drag have equivalents** `MUST · both`
Hover MUST have tap and focus equivalents. Drag MUST have a non-drag equivalent.

**ADP-14 · Gestures accelerate only** `MUST · both`
Gestures MUST NOT be the only path.

**ADP-27 · Stylus is pointer** `MUST · both`
Stylus input MUST be treated as pointer input.

### 7.6 Accessibility across contexts

**ADP-15 · Every representation passes** `MUST · both`
Every representation MUST meet 2.7 on its own.

**ADP-16 · Zoom is a container change** `MUST · both`
Zoom and text-size changes MUST be treated as container changes.

### 7.7 State

**ADP-17 · State survives resize and handoff** `MUST · both`
Scroll, open panels, selection, filters, sort and input MUST persist across resizing and handoff.

**ADP-18 · State survives representation changes** `MUST · system`
Switching representation MUST NOT reset contained state, and MUST keep accessible names, roles and order.

**ADP-19 · Persistent controls keep their own state** `MUST · both`
Persistent controls MUST keep their state independent of navigation and overlays.

**ADP-20 · Back restores exactly** `MUST · both`
Returning from a deeper level MUST restore the shallower one as it was.

### 7.8 Folds and split screens

**ADP-21 · Folding re-presents in place** `MUST · both`
Fold, unfold and posture changes MUST be container changes, re-presented in place without reload.

**ADP-22 · No assumed phone ratio** `MUST · both`
Layouts MUST NOT assume a tall phone ratio.

**ADP-23 · Nothing on the fold** `MUST · both`
Targets and critical text MUST NOT sit across a fold.

**ADP-26 · Works as half a screen** `MUST · both`
A view MUST work as one pane of a split view.

**ADP-28 · Thumb reach** `SHOULD · both`
Primary actions SHOULD stay within thumb reach on narrow screens.

---

## 8. Validation · VAL

### 8.1 System audit

Run once per system release. Its output is the conformance statement (0.5).

| # | Question | Checks |
|---|---|---|
| 1 | Every value a role-named token, machine-readable, validator-clean? | FND-31, FND-32 |
| 2 | Declared, related scales; one narrow spacing step? | FND-03, FND-06, FND-47, LAY-05 |
| 3 | Every theme meets contrast; fills have foregrounds; forced colours? | FND-21, FND-33 – FND-35 |
| 4 | Colour has four jobs, families reserved, nothing decorative? | FND-36, FND-38 – FND-40 |
| 5 | One emphasis treatment; two-signal active state? | FND-10, CMP-07, NAV-11 |
| 6 | True circles, no side stripes, one boundary, shadow only when floating? | FND-13, FND-41 – FND-44 |
| 7 | Focus, keyboard, targets, reflow for every component? | FND-16, FND-22, FND-23, FND-26, ADP-11, ADP-12 |
| 8 | Components honour their contract; one input family; native dialogs? | CMP-01 – CMP-06, CMP-22, CMP-25, CMP-28, CMP-31, CMP-35, CMP-39, CMP-40, CMP-42 |
| 9 | One frame; marker style; navigation compact and centred? | LAY-24, LAY-25, LAY-35, LAY-36, NAV-30, NAV-32, NAV-48 |
| 10 | Thresholds derived and owned; no device names? | ADP-01 – ADP-06 |
| 11 | Everything reachable at narrow, nothing wraps, truncation reversible? | ADP-07 – ADP-10, ADP-15 – ADP-18, ADP-30, ADP-31, NAV-18 – NAV-20 |
| 12 | Motion purposeful, interruptible, reducible? | FND-27 – FND-30 |
| 13 | Every `system` and `both` rule in the conformance statement? | VAL-05, VAL-06 |

### 8.2 View audit

Run in order. A failing MUST is recorded and fixed before later steps are judged, because they assume it holds; then the review continues to the end. Where a conformance statement marks a rule Met, cite it instead of re-checking the system's part (VAL-07).

| # | Question | Checks |
|---|---|---|
| 1 | What is this view for, in one sentence? | CTX-01, CTX-02, PRN-02 |
| 2 | Which 2–4 content types, each served? | CTX-04 – CTX-06 |
| 3 | Does the content match the budget? | CTX-07 – CTX-09, CTX-18, FND-08 |
| 4 | Disclosure level declared; primary first; advanced on request? | CTX-10 – CTX-14 |
| 5 | The user's job in one verb; pattern matches? | CTX-15, LAY-18 – LAY-23 |
| 6 | Hierarchy survives without decoration; one focal point per section? | CTX-17, PRN-04, FND-09, LAY-15 |
| 7 | One primary action, visibly weighted? | PRN-05, FND-10, LAY-10, CMP-04, CMP-07 |
| 8 | Hero within limits; next section peeks; strongest content next? | LAY-26 – LAY-28 |
| 9 | Title and actions share a row; one toolbar; nothing orphaned; balanced? | LAY-29 – LAY-34 |
| 10 | Frame shared; type levels; rhythm; spacing; markers? | LAY-24, LAY-01 – LAY-17, FND-01 – FND-07, FND-45 – FND-47, LAY-35 |
| 11 | Colour carries meaning; not monochrome; no decoration; artwork explains? | FND-36 – FND-40, FND-48 |
| 12 | No side stripes, no card-in-card, one boundary, true circles? | FND-41 – FND-44, FND-13 |
| 13 | Every state designed; status in three channels? | FND-17 – FND-20, CMP-03, CMP-31, CMP-43 – CMP-45 |
| 14 | Contrast, targets, keyboard, names, semantics, reflow? | FND-21 – FND-26, CMP-10, CMP-28 |
| 15 | One-word labels that never wrap; input family; native dialogs? | CMP-08, CMP-37 – CMP-42, CMP-11 – CMP-17 |
| 16 | Navigation: taxonomy, wide row, page context, search? | NAV-01 – NAV-15, NAV-28 – NAV-37, NAV-43, NAV-44 |
| 17 | Narrow: designed, two circles, utilities on top, nothing wraps, nothing lost? | ADP-07 – ADP-10, ADP-29 – ADP-32, NAV-18 – NAV-20, NAV-38 – NAV-42, NAV-45 |
| 18 | State survives resize, handoff, representation switch, drill-back? | ADP-17 – ADP-20, CTX-12, CMP-16, CMP-24 |
| 19 | Footer, persistent controls, in-page navigation? | NAV-16, NAV-17, NAV-21 – NAV-25, NAV-46, NAV-47 |
| 20 | Motion purposeful and reducible? | FND-27 – FND-30 |
| 21 | Every element earns its place; deviations recorded; final pass run? | PRN-11, PRN-13, VAL-08 |

**VAL-01 · Run the whole sequence** `MUST · review`
A review MUST run its full sequence and cite rule IDs for every finding.

**VAL-02 · Defects and deviations** `MUST · review`
A finding against a MUST is a **defect**; against a SHOULD without a recorded reason, a **deviation**. A MAY is never a finding.

**VAL-03 · Passing** `MUST · review`
A view or system MUST have zero defects and every deviation recorded before it passes.

### 8.3 Final pass

**VAL-08 · Run the final pass** `MUST · review`
Before anything is called done, it MUST be inspected at every test width (0.4) against this list, and every item fixed or recorded.

| Area | Inspect |
|---|---|
| Composition | Desktop, mid-width and narrow compositions; one focal point per section; symmetry |
| Header | Hero load; page heading and action balance; search and filter placement |
| Navigation | Compact row in the frame; centred wayfinding; utility cluster; narrow circles; search at top; back circle |
| Actions | One word; nothing wraps; one primary |
| Inputs | One family; every layer and state |
| Layers | Dialog native and proportionate; lightest layer chosen |
| Markers | One numeral-in-border style; no section sign |
| Footer | Compact bands; badges, not sentences |
| Colour | Meaning, not monochrome; no decoration |
| Artwork | Explains one idea; separate from controls |
| Type and space | Levels, rhythm, narrow spacing step, density |
| Overflow | Truncation reversible; nothing wraps awkwardly |
| Icons | Proportions: true circles, nothing stretched or boxed |
| Borders | No unnecessary borders, no side stripes, no card in a card |
| States and motion | Every interaction and content state; motion purposeful |
| Accessibility | Contrast, targets, keyboard, focus, reflow |
| Generated look | Nothing from the anti-pattern catalogue (8.5) remains |

### 8.4 Conformance

**VAL-05 · Publish a conformance statement** `MUST · system`
A system that claims conformance MUST publish a statement (0.5) listing every `system` and `both` rule with its outcome and evidence. An unmet MUST cannot be a deviation.

**VAL-06 · Pin the version** `MUST · system`
A conformance statement MUST name the exact version of this standard. A new major version requires a new statement.

**VAL-07 · Views inherit system results** `MUST · view`
A view audit MAY cite a conforming system's statement for rules marked Met. It MUST still check every Delegated rule and every `view` rule.

### 8.5 Anti-pattern catalogue

Symptoms in the words people use, and the generated-looking patterns behind them.

| Symptom or pattern | Failure | Rules |
|---|---|---|
| "It looks busy" | Decoration propping up structure | CTX-07, CTX-17, FND-13, FND-36 |
| "It looks AI-generated" | Hero overload, identical cards, gradients, blobs | LAY-26, LAY-34, FND-40, FND-48 |
| Headline, paragraph, badges, stats and logos in the hero | Hero as summary | LAY-26 |
| KPI tiles straight under the hero | Weak content first | LAY-28, CTX-18 |
| Cards in cards | Containment as decoration | FND-42 |
| Coloured stripe down one side of a card, quote or current item | Side stripe | FND-41 |
| Grey everywhere | Colour not doing its jobs | FND-37 |
| Rainbow strip, multicolour icons | Decorative colour | FND-36 |
| Oval "circle" buttons | False circles | FND-44 |
| "Create new workspace" wraps | Verbose label | CMP-08, CMP-37 |
| "Submit what?" / "Loved by thousands" | Vague labels or proof | CMP-08, CMP-33 |
| Search on one row, filters on another, a lone toggle far right | Toolbar not composed | LAY-30, LAY-31 |
| Everything the same size | Flat hierarchy | FND-45 |
| Desktop padding on a 320 px screen | Narrow not designed | ADP-29, FND-47 |
| Everything stacked single-file | Over-stacking | ADP-32 |
| Labels, chips or nav wrapping to two lines | Wrapping controls | ADP-30 |
| Numbers in hexagons; a section sign before headings | Decorative numbering | LAY-35, LAY-36 |
| Edge-to-edge opaque nav; items spread across the width | Navigation not compact | NAV-30, NAV-04 |
| A single floating pill of links on mobile | Wrong narrow navigation | NAV-40 |
| Search buried in the bottom dock | Search moved | NAV-39, NAV-43 |
| Big theme toggle switch | Preference not compact | NAV-44 |
| "← Back to all projects" | Text back link | NAV-34 |
| "Saved!" toast on every autosave | Noisy save state | NAV-35 |
| Footer wall of text and newsletter | Footer not a conclusion | NAV-25, NAV-47 |
| "Where am I?" | Exact-path or colour-only active state | NAV-10, NAV-11 |
| "The mobile menu is missing things" | Re-authored taxonomy | NAV-18, ADP-07 |
| "It resets when I resize" | State tied to representation | ADP-17, ADP-18 |
| "The page scrolls sideways" | Wide content not contained | LAY-04, ADP-04 |
| "Nothing happens on my phone" | Hover-only or drag-only | FND-17, ADP-13 |
| "Is this loading or broken?" | Undesigned states | FND-19, CMP-44 |
| "Oops! Something went wrong." | Error without a way forward | CMP-45 |
| Ten selects above a prompt | Options before the prompt | CMP-41 |
| Browser-default select beside a styled field | Broken input family | CMP-39 |
| Every canvas tool visible at once | Canvas not calm | CMP-46 |
| A centred box with huge padding and a heavy border | Generic dialog | CMP-42 |
| A page-level CSS override "to fix" a component | Patching the page | PRN-18 |

### 8.6 Report format

```
| # | Rule   | Level  | Location          | Finding                           | Fix                    |
|---|--------|--------|-------------------|-----------------------------------|------------------------|
| 1 | NAV-40 | MUST   | narrow navigation | single pill of five links         | menu + action circles  |
| 2 | CMP-37 | MUST   | page header       | "Create workspace" wraps at 360px | "Create"               |
| 3 | LAY-34 | SHOULD | home              | three identical feature cards     | lead item; or record   |
```

**VAL-04 · Findings cite rules** `MUST · review`
Every finding MUST name the rule, its level, the location and a fix. A finding without a rule ID is an opinion and MUST be mapped to a rule or proposed as a change.

---

## 9. Changes in 2.0

Rule IDs from 1.1 keep their numbers. ADP-24 and ADP-25 are retired and never reused. Every rule gained a title and a scope.

| Area | Change | Why |
|---|---|---|
| Vocabulary | "Surface" → **view**, "density" → **content budget**, "zone" → **navigation group**; **frame** added | The old words collided with common token names; the frame needed a name |
| Independence | Conformance moved to a separate statement (0.5) | The standard and any system can be read and versioned apart |
| Defaults | Numbers for every measurable quality (0.4) | "Compact" and "balanced" were not testable |
| PRN-18, PRN-19 | Fix the system; don't rationalise | Problems kept being patched per page |
| FND-36 – FND-40 | Four colour jobs, family vocabulary, no monochrome default, reserved status, gradients only encode | "One accent used sparingly" produced grey interfaces and rainbow decoration in turn |
| FND-41 – FND-44 | No side stripes, containers earn their place, one boundary, true circles | The most repeated generated-looking defects |
| FND-45 – FND-48 | Text levels, rhythm, one narrow spacing step, artwork rules | Flat hierarchy, per-page paddings, filler graphics |
| CTX-18 | Dashboards only for monitoring | Metric grids were the default composition |
| LAY-24, LAY-25 | One frame shared by navigation, content and footer | Navigation, content and footer drifted out of alignment |
| LAY-26 – LAY-34 | Hero limits, page header and toolbar composition, balance | Overloaded heroes and orphaned controls |
| LAY-35, LAY-36 | One section-marker style; no section sign | Inconsistent, decorative numbering |
| NAV-01 | Three groups now form one compact row in the frame | "Floating zones" became a collection of loose controls |
| NAV-07 | Groups route to hubs; dropdowns optional | Carets on every item made navigation heavy |
| NAV-13, NAV-15 | One grouped menu; preferences inside it | Utility clusters grew |
| NAV-17, NAV-21 | Persistent controls sit between the narrow circles | Narrow navigation changed shape |
| NAV-22, NAV-25 | Footer compact; columns only when useful | 1.1 required both "two columns" and "three or more" |
| NAV-28 – NAV-48 | Taxonomy as data, wide row rules, back circle, save state, narrow structure, search at top, compact preferences, footer metadata | The icon dock and floating controls kept reappearing as defects |
| CMP-08 | Verb phrases → one word | Labels wrapped and crowded |
| CMP-11 | Labels above or stacked inside | Layered inputs are allowed |
| CMP-37 – CMP-46 | Label wrapping, feedback words, input family, prompt inputs, native dialogs, empty/loading/error, canvas | Inconsistent inputs and generic dialogs |
| ADP-29 – ADP-33 | Narrow is designed; no wrapping controls; truncation table; no over-stacking; independent widths | Narrow layouts were shrunk desktops |
| ADP-24, ADP-25 | Retired (hinge split, companion screen) | Rarely applicable; the remaining fold rules cover the cases |
| VAL-08, 8.5 | Final pass and anti-pattern catalogue | Reviews stopped at "functional" |
