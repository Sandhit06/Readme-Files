# The Complete Frontend Development Guide — Basics to Advanced

### HTML • CSS • JavaScript • TypeScript • React • GSAP & Animation • Interview Mastery

---

## How To Use This Guide

This is a single, self-contained reference that takes you from "I've never written a line of
HTML" to "I can architect, animate, optimize, and defend a production frontend in a system
design or coding interview." It is organized as 15 parts. You do not have to read it in one
sitting — treat it like a textbook you keep coming back to.

- **If you are a complete beginner**: start at Part 1 and go in order through Part 7. Do not
  skip the JavaScript part to jump to React — 90% of "React is confusing" complaints are
  actually "JavaScript closures/this/async are confusing."
- **If you already code but want to get serious about animation**: read Part 8 closely, but
  make sure you've internalized the CSS transforms/opacity performance material in Part 3.6
  and the browser rendering pipeline in Part 6.5 first — animation performance problems are
  almost always rendering-pipeline problems in disguise.
- **If you are prepping for interviews in the next few weeks**: go straight to Part 13
  (Frontend System Design) and Part 14 (Interview Q&A Bank), then circle back to fill gaps
  using the earlier parts as a reference.
- **Every code sample is meant to be typed out, not just read.** Open a scratch file (or
  codesandbox.io / stackblitz.com / plain `index.html` + `<script>` tag) and run it. Frontend
  is a hands-on discipline — reading about a CSS Grid layout is not the same as fighting with
  one for ten minutes.

---

## Table of Contents

1. Frontend Foundations & Mental Model
2. HTML5 — Structure, Semantics, Forms, Accessibility Basics
3. CSS — From Box Model to Advanced Layout & Animation
4. JavaScript — Fundamentals to Advanced (the real heart of frontend)
5. TypeScript — Types That Actually Help You
6. The DOM, Browser APIs & the Rendering Pipeline
7. React — Components, Hooks, State, Performance, Ecosystem
8. Animation Deep Dive — CSS, GSAP, ScrollTrigger, Framer Motion, FLIP, 60fps Discipline
9. Build Tools & Tooling — npm/Vite/Webpack/Babel/ESLint
10. Testing the Frontend — Unit, Component, and E2E
11. Performance & Core Web Vitals
12. Accessibility (a11y) — Building for Everyone
13. Frontend System Design for Interviews
14. Interview Question & Answer Bank (HTML/CSS/JS/TS/React/Animation/System Design/Coding)
15. Cheat Sheets, Glossary, Study Roadmap & Closing Notes

---

# Part 1 — Frontend Foundations & Mental Model

## 1.1 What "Frontend" Actually Means

Frontend development is the practice of building everything a user directly sees and
interacts with in a browser (or a webview inside a mobile app). At its core, every frontend,
no matter how fancy the framework, boils down to three technologies the browser understands
natively:

| Technology | Job | Analogy |
|---|---|---|
| HTML | Structure & meaning of content | The skeleton of a body |
| CSS | Presentation, layout, visual styling | The skin, clothes, posture |
| JavaScript | Behavior, interactivity, data, logic | The muscles & nervous system |

Frameworks like React, Vue, Angular, and Svelte do not replace these three — they are
abstractions written **in** JavaScript that generate HTML and manipulate the DOM (Document
Object Model) more efficiently and with better developer ergonomics than doing it by hand.
TypeScript is a superset of JavaScript that adds a type system on top; it compiles down to
plain JavaScript before it ever reaches a browser. GSAP is a JavaScript animation library.
Understanding this hierarchy — **browser primitives at the bottom, libraries/frameworks on
top** — is the single most important mental model for a frontend engineer, because it means
you can always answer "what is this abstraction actually doing under the hood?"

## 1.2 The Browser's Job, In One Paragraph

When you type a URL and hit enter: the browser resolves DNS, opens a TCP/TLS connection,
sends an HTTP request, and receives back an HTML document (usually). It parses that HTML into
a tree of nodes called the **DOM**. While parsing, whenever it encounters a `<link rel="stylesheet">`
or `<style>` it builds a second tree called the **CSSOM** (CSS Object Model). It combines DOM +
CSSOM into a **render tree**, computes the geometry of every visible box (**layout/reflow**),
paints pixels for each box (**paint**), and finally composites painted layers onto the screen
(**composite**). Whenever you encounter a `<script>` tag, the browser (by default) pauses
HTML parsing, downloads (if external) and executes the JavaScript, because JS can use
`document.write` or DOM APIs that change what should be parsed next. This is why `async`/
`defer` attributes and script placement matter so much for perceived performance — we go deep
on this in Part 6.5 and Part 11.

## 1.3 Client-Side vs Server-Side vs Hybrid Rendering

- **Client-Side Rendering (CSR)**: server sends a nearly-empty HTML shell + a JS bundle; the
  browser downloads and executes JS, which then builds the entire UI in the DOM. Classic
  create-react-app style SPA (Single Page Application). Pro: rich interactivity, app-like
  feel, no full page reloads on navigation. Con: slow "time to first meaningful paint" because
  nothing shows until JS downloads+executes; bad for SEO unless mitigated.
- **Server-Side Rendering (SSR)**: the server runs your framework's rendering code (e.g.
  React's `renderToString`) to produce full HTML on every request, sends that to the browser,
  then JS "hydrates" it (attaches event listeners to the existing markup) to make it
  interactive. Pro: fast first paint, good SEO. Con: server compute cost, hydration
  complexity/mismatches.
- **Static Site Generation (SSG)**: HTML is generated once at build time (not per-request) and
  served from a CDN. Fastest possible delivery, ideal for content that doesn't change per
  user (blogs, docs, marketing pages). Next.js, Astro, Gatsby popularize this.
- **Incremental Static Regeneration (ISR)** / streaming SSR / islands architecture: modern
  hybrids that regenerate static pages on a schedule or stream HTML in pieces as it becomes
  ready, popularized by Next.js (`revalidate`) and frameworks like Astro/Qwik ("islands" —
  only interactive components ship JS, the rest stays static HTML).

This is a spectrum, not a binary choice, and you will be asked about these tradeoffs in senior
frontend interviews (see Part 13).

## 1.4 The Modern Frontend Toolchain, End to End

```
Your source code (.jsx/.tsx/.ts/.scss)
        │
        ▼
  Transpiler (Babel / SWC / TS compiler) — converts modern/JSX/TS syntax to
        │                                   plain JS the target browsers understand
        ▼
  Bundler (Vite / Webpack / esbuild / Rollup) — resolves imports, tree-shakes
        │                                        dead code, splits into chunks
        ▼
  Dev server (HMR) during development, OR
  Optimized static assets (minified JS/CSS, hashed filenames) for production
        │
        ▼
  CDN / static host / Node server — serves the assets to real browsers
        │
        ▼
  Browser: parse HTML → CSSOM → render tree → layout → paint → composite
        │
        ▼
  Your JS framework "hydrates" or "mounts", attaches event listeners, app is alive
```

Every box in that diagram is something we will unpack in this guide: Babel/SWC and JSX in
Part 7, bundlers in Part 9, the browser pipeline in Part 6.5.

## 1.5 How To Actually Learn This (Study Discipline)

1. **Type every example** — muscle memory for syntax matters more than people admit.
2. **Break things on purpose** — comment out a `key` prop in a React list, remove `display:
   flex`, forget `await` — and observe exactly what breaks. This builds the debugging
   intuition interviews probe for.
3. **Build, don't just tutorial-follow** — after each Part, build one tiny real project using
   only what you've learned so far (a to-do list after Part 4, a component library after
   Part 7, an animated landing page after Part 8).
4. **Read browser errors character by character** — "Cannot read properties of undefined
   (reading 'map')" always means the array you expected is `undefined`; find why.
5. Use the browser DevTools constantly: Elements tab (live DOM+CSS), Console, Network,
   Performance/Lighthouse, and the React/Redux DevTools extensions once you get to Part 7.

---

# Part 2 — HTML5: Structure, Semantics, Forms, Accessibility Basics

## 2.1 Anatomy of an HTML Document

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>My Page</title>
  <meta name="description" content="A short, accurate summary for search engines." />
  <link rel="stylesheet" href="styles.css" />
</head>
<body>
  <header>...</header>
  <main>...</main>
  <footer>...</footer>
  <script src="app.js" defer></script>
</body>
</html>
```

- `<!DOCTYPE html>` triggers **standards mode** rendering in all modern browsers (omit it and
  you get "quirks mode," a legacy compatibility mode with different box-sizing/layout rules —
  always include it).
- `<meta charset="UTF-8">` must be within the first 1024 bytes of the document; without it,
  special characters can render as mojibake.
- `<meta name="viewport" ...>` is mandatory for any responsive design — without it, mobile
  browsers render the page at a fixed desktop-like width (usually 980px) and scale it down.
- Placing `<script>` at the end of `<body>`, or using the `defer` attribute, prevents
  render-blocking — the browser can continue parsing/painting HTML while JS downloads in the
  background, then execute it once parsing is done, in document order. `async` downloads in
  parallel too, but executes **as soon as it's ready**, potentially out of order with other
  scripts — good for independent scripts (analytics), bad for scripts with load-order
  dependencies.

## 2.2 Semantic HTML — Why Tags Have Meaning

Semantic HTML means choosing tags based on **what the content is**, not what it looks like.
`<div>` and `<span>` carry zero meaning — they are generic boxes. Compare:

```html
<!-- Non-semantic: a screen reader or search engine has no idea what this is -->
<div class="header">
  <div class="nav">
    <div class="nav-item">Home</div>
  </div>
</div>

<!-- Semantic: meaning is baked into the markup itself -->
<header>
  <nav>
    <a href="/">Home</a>
  </nav>
</header>
```

Key semantic elements and when to use them:

| Element | Purpose |
|---|---|
| `<header>` | Introductory content or navigation for its nearest sectioning ancestor |
| `<nav>` | A block of major navigation links |
| `<main>` | The dominant, unique content of the document (only one per page) |
| `<article>` | Self-contained, independently distributable content (a blog post, a card) |
| `<section>` | A thematic grouping of content, usually with its own heading |
| `<aside>` | Content tangentially related to the main content (sidebars, pull-quotes) |
| `<footer>` | Footer for its nearest sectioning ancestor |
| `<figure>`/`<figcaption>` | Self-contained media (image/diagram) with an optional caption |
| `<time datetime="2026-01-01">` | Machine-readable dates/times |
| `<mark>` | Highlighted/relevant text |
| `<address>` | Contact information |

Why this matters beyond "best practice": screen readers build a **navigation landmark tree**
from these tags so blind users can jump straight to `<nav>` or `<main>`; search engines weight
`<article>`/`<h1>`-`<h6>` content more heavily for indexing; and browser extensions/reader-mode
features (like Safari Reader) rely entirely on this structure to extract "the article."

## 2.3 Headings & Document Outline

Use exactly one `<h1>` per page (the page's main title) and never skip heading levels purely
for font-size reasons (e.g., don't jump from `<h2>` to `<h4>` just because `<h4>` looks like
the right size — style it with CSS instead). Screen reader users frequently navigate by
heading level; a broken hierarchy is disorienting for them even if sighted users never notice.

## 2.4 Forms — The Most Under-Appreciated Part of HTML

Forms are deceptively deep. A well-built form uses native HTML validation, correct input
types, and label association before a single line of JavaScript is written.

```html
<form action="/submit" method="POST" novalidate>
  <div>
    <label for="email">Email</label>
    <input
      type="email"
      id="email"
      name="email"
      required
      autocomplete="email"
      aria-describedby="email-error"
    />
    <span id="email-error" role="alert"></span>
  </div>

  <div>
    <label for="age">Age</label>
    <input type="number" id="age" name="age" min="18" max="120" />
  </div>

  <fieldset>
    <legend>Preferred contact method</legend>
    <label><input type="radio" name="contact" value="email" checked /> Email</label>
    <label><input type="radio" name="contact" value="phone" /> Phone</label>
  </fieldset>

  <label>
    <input type="checkbox" name="subscribe" />
    Subscribe to newsletter
  </label>

  <button type="submit">Send</button>
</form>
```

Key points:
- **`<label for="id">` must match the input's `id`** (or wrap the input) — this is what lets
  clicking the label focus the input, and is *required* for screen readers to announce what
  the field is for. A `<div>` styled to look like a label does none of this for free.
- **Use the right `type`** (`email`, `tel`, `number`, `date`, `url`, `search`, `password`) —
  this changes the on-screen keyboard on mobile (e.g., `type="tel"` shows a numeric keypad)
  and enables free browser-native validation.
- **`required`, `min`, `max`, `minlength`, `maxlength`, `pattern`** give you client-side
  validation with zero JavaScript. `novalidate` on the `<form>` disables native validation so
  you can implement custom UX around it (still validate on the server regardless — client
  validation is a UX nicety, never a security boundary).
- **`<fieldset>`/`<legend>`** groups related controls (like a radio button group) and gives
  assistive tech an accessible group name.
- **`autocomplete` attributes** (`email`, `name`, `street-address`, `cc-number`, etc.) let
  browsers/password managers autofill correctly — huge UX win, often skipped.
- **`name` attribute is what actually gets submitted** — `id` is for CSS/JS/labels only; a
  form control without a `name` is silently omitted from form submission data.

### Form Submission: Traditional vs JS-Driven

A plain `<form action="/api/submit" method="POST">` causes a **full page navigation** — the
browser serializes the form data (as `application/x-www-form-urlencoded` or
`multipart/form-data` if there's a file input) and POSTs it, then renders whatever HTML comes
back. In modern SPAs we usually intercept this:

```js
form.addEventListener('submit', async (e) => {
  e.preventDefault(); // stop the full page reload
  const data = new FormData(form);
  const res = await fetch('/api/submit', { method: 'POST', body: data });
  if (!res.ok) {
    // show inline error, don't lose user's input
  }
});
```

`e.preventDefault()` is the single most important line here — forgetting it is the #1 cause
of "my React form just refreshes the page" bugs for beginners.

## 2.5 Images, Media & Responsive Assets

```html
<img
  src="hero-800.jpg"
  srcset="hero-400.jpg 400w, hero-800.jpg 800w, hero-1600.jpg 1600w"
  sizes="(max-width: 600px) 100vw, 50vw"
  alt="A mountain landscape at sunset"
  loading="lazy"
  width="800"
  height="450"
/>
```

- `alt` is **not optional** for meaningful images — it's what a screen reader announces, and
  what shows if the image fails to load. Decorative images that add no information should use
  `alt=""` (empty, not omitted) so screen readers skip them entirely.
- `srcset`/`sizes` let the browser pick the best-fitting image for the viewport/pixel density,
  saving bandwidth on mobile.
- `loading="lazy"` defers offscreen images until the user scrolls near them — free performance
  win built into the platform, no JS library needed.
- Always set `width`/`height` (or `aspect-ratio` in CSS) so the browser can reserve the correct
  space before the image loads, preventing **layout shift** (a Core Web Vitals metric, see
  Part 11).
- `<picture>` lets you serve different formats/art direction:

```html
<picture>
  <source srcset="hero.avif" type="image/avif" />
  <source srcset="hero.webp" type="image/webp" />
  <img src="hero.jpg" alt="A mountain landscape at sunset" />
</picture>
```
The browser picks the first `<source>` it supports, falling back to `<img>` — great for
shipping next-gen formats (AVIF/WebP) with a safe fallback.

## 2.6 HTML Tables — For Tabular Data Only

```html
<table>
  <caption>Q1 Sales by Region</caption>
  <thead>
    <tr><th scope="col">Region</th><th scope="col">Revenue</th></tr>
  </thead>
  <tbody>
    <tr><th scope="row">West</th><td>$120,000</td></tr>
    <tr><th scope="row">East</th><td>$98,000</td></tr>
  </tbody>
</table>
```
Never use `<table>` for page layout (a common pre-CSS-era hack) — it's an accessibility and
semantic disaster on modern devices. `scope="col"`/`scope="row"` help screen readers associate
cells with their headers.

## 2.7 Web Components (Custom Elements) — A Quick Look

Even without React/Vue, the browser natively supports building reusable, encapsulated
components via three APIs working together:

```js
class MyCounter extends HTMLElement {
  constructor() {
    super();
    this.attachShadow({ mode: 'open' }); // Shadow DOM: encapsulated styles/markup
    this._count = 0;
  }
  connectedCallback() {
    this.shadowRoot.innerHTML = `
      <style>button { font-size: 1.2rem; }</style>
      <button>Count: ${this._count}</button>
    `;
    this.shadowRoot.querySelector('button').addEventListener('click', () => {
      this._count++;
      this.shadowRoot.querySelector('button').textContent = `Count: ${this._count}`;
    });
  }
}
customElements.define('my-counter', MyCounter);
```
Usage: `<my-counter></my-counter>` in any HTML page, framework or not. This underpins design
systems like Shoelace and is worth knowing conceptually even if you spend your career in
React, because interviewers sometimes ask "how would you build a reusable component without a
framework?"

## 2.8 HTML Accessibility Basics (deep dive continues in Part 12)

- Every interactive element should be reachable and operable via **keyboard alone** (Tab,
  Shift+Tab, Enter, Space, arrow keys for composite widgets). Native elements (`<button>`,
  `<a href>`, `<input>`) get this for free; a `<div onClick>` does not.
- Use `<button>` for actions, `<a href="...">` for navigation — not the other way around. A
  `<div>` styled as a button needs `tabindex="0"`, `role="button"`, and manual `keydown`
  handling to match — just use `<button>`.
- `aria-label`, `aria-labelledby`, `aria-describedby` supply accessible names/descriptions when
  visible text isn't enough (e.g., an icon-only close button: `<button aria-label="Close
  dialog">✕</button>`).
- `aria-live="polite"`/`"assertive"` regions announce dynamic content changes (toast
  notifications, form errors) to screen readers without moving focus.

---

# Part 3 — CSS: From Box Model to Advanced Layout & Animation

## 3.1 The Box Model — Everything Is a Box

Every element on a page is a rectangular box made of four layers, from inside out:

```
┌───────────────────────────────┐
│           margin               │  (transparent, pushes other elements away)
│  ┌───────────────────────────┐ │
│  │         border            │ │  (visible line around the box)
│  │  ┌───────────────────────┐│ │
│  │  │       padding          ││ │  (space between border and content)
│  │  │  ┌───────────────────┐ ││ │
│  │  │  │      content       │ ││ │  (text/images/children)
│  │  │  └───────────────────┘ ││ │
│  │  └───────────────────────┘│ │
│  └───────────────────────────┘ │
└───────────────────────────────┘
```

```css
.box {
  width: 300px;
  padding: 20px;
  border: 2px solid black;
  margin: 10px;
}
```

By default (`box-sizing: content-box`), `width` applies only to the **content** box — the
actual rendered width becomes `300 + 20*2 + 2*2 = 344px`, which surprises nearly every
beginner. The fix, applied almost universally in real projects:

```css
*, *::before, *::after {
  box-sizing: border-box; /* width/height now INCLUDE padding + border */
}
```

With `border-box`, `width: 300px` means the box is **always** 300px wide total, and the
content area shrinks to accommodate padding/border. This one rule eliminates an entire class
of layout bugs and should be in literally every project's global stylesheet.

### Margin Collapsing (a classic gotcha)

Vertically adjacent margins between block-level siblings **collapse** into a single margin
(the larger of the two), not the sum:

```css
.a { margin-bottom: 20px; }
.b { margin-top: 30px; }
/* Gap between .a and .b is 30px, NOT 50px */
```
This only happens for **vertical** margins of **block** boxes in normal flow (not flex/grid
children, not elements with `overflow` other than `visible`, not floated/absolutely positioned
elements). Interviewers love asking "why is the gap between these two divs smaller than
expected?" — margin collapsing is almost always the answer.

## 3.2 Selectors, Specificity & the Cascade

CSS resolves conflicting rules using a well-defined algorithm: **origin & importance**, then
**specificity**, then **source order**.

### Specificity Calculation
Specificity is a 3-part tuple **(IDs, classes/attributes/pseudo-classes, elements/pseudo-elements)**:

| Selector | Specificity (id, class, element) |
|---|---|
| `div` | (0,0,1) |
| `.card` | (0,1,0) |
| `#header` | (1,0,0) |
| `div.card` | (0,1,1) |
| `#header .nav a` | (1,1,1) |
| `style="..."` inline | beats all normal specificity tuples |
| `!important` | beats everything else in the same origin (avoid it) |

Higher tuples win, compared left to right — a single ID (1,0,0) always beats any number of
classes (0,N,0). When specificity ties, the rule that appears **later** in the source wins.

```css
.btn { color: blue; }       /* (0,1,0) */
.btn.primary { color: red; } /* (0,2,0) — this wins, more specific */
```

### The Cascade Layers (`@layer`) — Modern CSS

```css
@layer reset, base, components, utilities;

@layer base {
  a { color: blue; }
}
@layer utilities {
  .text-red { color: red; } /* wins over @layer base even with LOWER specificity,
                                because utilities layer is declared later */
}
```
`@layer` lets teams control cascade priority **by architecture**, independent of specificity
wars — hugely useful in design systems, and increasingly asked about in senior interviews.

## 3.3 Positioning

| `position` value | Behavior |
|---|---|
| `static` (default) | Normal document flow; `top`/`left`/etc. have no effect |
| `relative` | Stays in normal flow, but `top`/`left`/etc. offset it *from where it would have been*; establishes a positioning context for `absolute` children |
| `absolute` | Removed from normal flow; positioned relative to the nearest **positioned** ancestor (any ancestor with `position` other than `static`), or the viewport if none |
| `fixed` | Removed from normal flow; positioned relative to the viewport, stays put during scroll |
| `sticky` | Behaves like `relative` until a scroll threshold (`top: 0`) is crossed, then behaves like `fixed` within its containing block |

```css
.dropdown {
  position: relative; /* anchor point */
}
.dropdown-menu {
  position: absolute;
  top: 100%;
  left: 0;
  /* positioned relative to .dropdown, not the page */
}
```

The classic interview trap: "why doesn't `position: absolute` respect my parent?" — answer:
the parent needs `position: relative` (or any non-static value) or the absolutely positioned
element escapes all the way up to the nearest positioned ancestor (often `<body>`/viewport).

## 3.4 Flexbox — One-Dimensional Layout

Flexbox distributes space along a single axis (row or column) and is the right tool for
navbars, toolbars, centering content, and equal-height cards.

```css
.container {
  display: flex;
  flex-direction: row;       /* row | row-reverse | column | column-reverse */
  justify-content: space-between; /* main-axis alignment */
  align-items: center;       /* cross-axis alignment */
  flex-wrap: wrap;           /* allow items to wrap to new lines */
  gap: 16px;                 /* spacing between items, no margin hacks needed */
}
.item {
  flex: 1 1 200px; /* grow shrink basis — shorthand you should memorize */
}
```

### `flex` Shorthand Deconstructed
`flex: <grow> <shrink> <basis>`
- **grow**: how much of the *extra* free space this item claims relative to siblings (0 =
  don't grow).
- **shrink**: how much this item shrinks relative to siblings when there's *not enough* space
  (0 = never shrink below its basis).
- **basis**: the item's starting size before growing/shrinking is applied (`auto` = use its
  content/width).

Common patterns:
```css
.equal-columns > * { flex: 1; }              /* all items share space equally */
.sidebar { flex: 0 0 250px; }                /* fixed width, never grows/shrinks */
.main-content { flex: 1 1 auto; }            /* takes remaining space */
```

### `justify-content` vs `align-items` — Never Confuse These Again

Both describe alignment, but on **different axes**, and the axis flips with `flex-direction`:
- `justify-content` → aligns along the **main axis** (the direction items are laid out: the
  `flex-direction`).
- `align-items` → aligns along the **cross axis** (perpendicular to `flex-direction`).

So in `flex-direction: row` (default), `justify-content` is horizontal and `align-items` is
vertical. Flip to `flex-direction: column` and it reverses — `justify-content` becomes
vertical, `align-items` becomes horizontal. This axis-flip is the #1 source of "why isn't my
centering working" bugs.

```css
/* Perfectly center anything, the single most-asked CSS interview snippet */
.center {
  display: flex;
  justify-content: center;
  align-items: center;
  min-height: 100vh;
}
```

## 3.5 CSS Grid — Two-Dimensional Layout

Grid handles rows **and** columns simultaneously — the right tool for page layouts, image
galleries, dashboards, anything with a genuine 2D structure.

```css
.layout {
  display: grid;
  grid-template-columns: 250px 1fr;   /* sidebar fixed, content fills rest */
  grid-template-rows: auto 1fr auto;  /* header / body / footer */
  grid-template-areas:
    "sidebar header"
    "sidebar content"
    "sidebar footer";
  min-height: 100vh;
  gap: 16px;
}
.header   { grid-area: header; }
.sidebar  { grid-area: sidebar; }
.content  { grid-area: content; }
.footer   { grid-area: footer; }
```

### `fr` Unit & `repeat()`

`fr` (fraction) divides remaining space proportionally after fixed-size tracks are subtracted:
```css
.gallery {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
  gap: 12px;
}
```
`repeat(auto-fill, minmax(200px, 1fr))` is the single most useful line in responsive Grid — it
creates as many 200px+ columns as fit the container, each stretching to fill leftover space,
**with zero media queries**. `auto-fill` keeps empty tracks if there's extra room;
`auto-fit` collapses empty tracks so existing items stretch to fill the row — subtle but
frequently asked distinction.

### Grid vs Flexbox — The Interview Answer

> "Flexbox is one-dimensional (you're really only controlling one axis at a time, even though
> wrapping *simulates* two dimensions); Grid is natively two-dimensional and lets you define
> both rows and columns, and explicitly place items into named areas. Rule of thumb: if you're
> laying out a full page/dashboard/gallery with real rows and columns, reach for Grid; if
> you're aligning items in a single row or column (navbar, button group, centering a modal),
> reach for Flexbox. They compose — Grid for the page skeleton, Flexbox inside individual grid
> cells is extremely common."

## 3.6 Transforms, Transitions & the Performance Story

```css
.card {
  transition: transform 0.2s ease-out, box-shadow 0.2s ease-out;
}
.card:hover {
  transform: translateY(-4px) scale(1.02);
  box-shadow: 0 10px 20px rgba(0,0,0,0.15);
}
```

**Why `transform`/`opacity` are the only properties you should animate for performance:**
changing `transform` or `opacity` can be handled entirely on the **compositor thread** — the
browser doesn't need to re-run layout or repaint pixels, it just re-composites existing painted
layers (like moving/fading a pre-rendered image), which can happen at a steady 60fps even
while the main JS thread is busy. Animating `width`, `height`, `top`, `left`, `margin`, etc.
triggers **layout** (recalculating geometry of potentially the whole page) on every frame,
which is drastically more expensive and the #1 cause of janky animations. This single fact —
"animate transform/opacity, not layout properties" — is one of the most-tested pieces of
frontend performance knowledge in interviews, and directly sets up everything in Part 8
(GSAP/animation).

`will-change: transform;` is a hint to the browser to promote an element to its own
compositor layer *ahead of time*, avoiding a stutter on the first frame of animation — but
overusing it wastes GPU memory (every promoted layer costs memory), so apply it just before an
animation starts and remove it after, rather than leaving it on permanently.

## 3.7 CSS Animations & Keyframes

```css
@keyframes pulse {
  0%   { transform: scale(1);   opacity: 1; }
  50%  { transform: scale(1.1); opacity: 0.7; }
  100% { transform: scale(1);   opacity: 1; }
}
.notification-dot {
  animation: pulse 1.5s ease-in-out infinite;
}
```

Keyframe animation properties worth memorizing:
- `animation-duration`, `animation-timing-function` (easing curve), `animation-delay`
- `animation-iteration-count` (`infinite` or a number), `animation-direction`
  (`normal`/`reverse`/`alternate`)
- `animation-fill-mode`: `forwards` keeps the last keyframe's styles after finishing (very
  commonly needed and very commonly forgotten — without it, the element snaps back to its
  pre-animation styles the instant the animation ends).
- `animation-play-state: paused` lets you pause/resume via JS/CSS class toggling without
  restarting.

CSS animations are declarative and great for simple, self-contained effects (spinners, pulses,
simple entrances). For anything sequenced, interruptible, scroll-driven, or physics-based,
you graduate to JavaScript-driven animation — GSAP — covered in full in Part 8.

## 3.8 Responsive Design & Media Queries

```css
/* Mobile-first: base styles are for the smallest screens, then progressively enhance */
.container {
  padding: 12px;
}
@media (min-width: 768px) {
  .container { padding: 24px; }
}
@media (min-width: 1200px) {
  .container { padding: 40px; max-width: 1140px; margin-inline: auto; }
}
```

**Mobile-first vs desktop-first**: mobile-first (using `min-width` breakpoints, styling up
from the smallest screen) is the modern default — it forces you to design the constrained
case first (which is harder) and matches the fact that most global web traffic is mobile.

Modern responsive tools beyond media queries:
- **Container queries** (`@container`) — style a component based on the size of its
  **container**, not the viewport, enabling truly reusable components that adapt regardless
  of where they're placed on the page:
```css
.card-container { container-type: inline-size; }
@container (min-width: 400px) {
  .card { flex-direction: row; }
}
```
- **Fluid typography with `clamp()`**:
```css
h1 { font-size: clamp(1.5rem, 4vw + 1rem, 3rem); }
/* never smaller than 1.5rem, never larger than 3rem, scales fluidly between */
```
- **Logical properties** (`margin-inline`, `padding-block`, etc.) adapt automatically to
  writing direction (LTR/RTL/vertical scripts) instead of hardcoding `left`/`right`.

## 3.9 CSS Custom Properties (Variables)

```css
:root {
  --color-primary: #3b82f6;
  --color-primary-dark: #1e40af;
  --spacing-unit: 8px;
  --radius: 12px;
}
.button {
  background: var(--color-primary);
  padding: calc(var(--spacing-unit) * 2);
  border-radius: var(--radius);
}
.button:hover {
  background: var(--color-primary-dark);
}
```

Unlike SASS variables (which are compile-time constants baked into the output CSS), CSS
custom properties are **live at runtime** — you can read/change them via JavaScript
(`el.style.setProperty('--color-primary', 'red')`), they cascade and can be overridden per
selector/media-query, and they're the backbone of modern theming (light/dark mode):

```css
:root { --bg: white; --fg: black; }
[data-theme="dark"] { --bg: #121212; --fg: #f5f5f5; }
body { background: var(--bg); color: var(--fg); }
```
Toggling `document.documentElement.dataset.theme = 'dark'` in JS instantly re-themes the
entire page — no re-render, no JS framework needed, purely CSS cascade doing the work.

## 3.10 Preprocessors — SASS/SCSS

```scss
$primary: #3b82f6;
@mixin flex-center($direction: row) {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: $direction;
}
.card {
  @include flex-center(column);
  &:hover { border-color: $primary; }
  .title { font-weight: bold; }
}
```
Compiles to plain nested-free CSS. SASS gives you variables (compile-time), nesting, mixins
(reusable style blocks with parameters), `@extend` (share rules between selectors), and
functions (`darken()`, `lighten()`) — genuinely useful, though native CSS custom properties,
nesting (`&` now works in plain CSS too), and `@layer` have closed much of the historical gap
that made SASS mandatory.

## 3.11 Naming Methodologies — BEM

```css
/* Block Element Modifier */
.card { }                 /* Block */
.card__title { }          /* Element (double underscore) */
.card__title--large { }   /* Modifier (double hyphen) */
.card--featured { }       /* Modifier on the block itself */
```
```html
<div class="card card--featured">
  <h3 class="card__title card__title--large">Hello</h3>
</div>
```
BEM's entire value proposition: **flat specificity** (everything is a single class, so
specificity wars never happen) and **self-documenting structure** (you can tell a class's role
and relationship to its block just by reading the name), at the cost of verbose class names.
Utility-first frameworks (Tailwind) and CSS-in-JS (scoped styles) solve the same underlying
problem — CSS's global namespace and specificity footguns — via different mechanisms; expect
to be asked to compare these approaches (see Part 14).

## 3.12 CSS-in-JS & Utility-First CSS (Conceptual Overview)

- **CSS-in-JS** (styled-components, Emotion): write CSS as JS template literals scoped to a
  component; the library generates unique class names at runtime/build time, eliminating
  global namespace collisions entirely and allowing styles to reference JS props/theme
  directly.
```jsx
const Button = styled.button`
  background: ${props => props.primary ? '#3b82f6' : '#e5e7eb'};
  padding: 8px 16px;
  border-radius: 8px;
`;
```
- **Utility-first CSS** (Tailwind CSS): compose pre-defined single-purpose classes directly in
  markup instead of writing custom CSS files.
```html
<button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded">
  Click me
</button>
```
Tradeoffs interviewers probe: Tailwind trades "readable, verbose HTML" for "no context
switching between files, no naming things, tiny final CSS bundle via purge/JIT"; CSS-in-JS
trades "runtime/build overhead + extra dependency" for "true colocation of styles with logic +
dynamic styling from props without manual class toggling."

---

# Part 4 — JavaScript: Fundamentals to Advanced

JavaScript is the actual heart of frontend engineering. React, Vue, GSAP — all of them are
just JavaScript. If you deeply understand this Part, frameworks become "syntax sugar over
things I already understand," which is exactly the mindset senior interviewers are listening
for.

## 4.1 Values, Types & Coercion

JavaScript has 8 data types: 7 **primitives** (`string`, `number`, `bigint`, `boolean`,
`undefined`, `symbol`, `null`) and `object` (which includes arrays, functions, dates, maps,
sets — everything non-primitive).

```js
typeof "hello"     // "string"
typeof 42          // "number"
typeof true        // "boolean"
typeof undefined   // "undefined"
typeof null        // "object"  <-- famous historical bug, never fixed for compatibility
typeof Symbol()    // "symbol"
typeof 10n         // "bigint"
typeof {}          // "object"
typeof []          // "object"  <-- use Array.isArray() to distinguish from plain objects
typeof function(){} // "function"
```

Primitives are **immutable and compared by value**; objects are **compared by reference**:
```js
let a = { x: 1 };
let b = { x: 1 };
console.log(a === b); // false — different references
console.log(a === a); // true  — same reference

let s1 = "hi", s2 = "hi";
console.log(s1 === s2); // true — primitives compare by value
```

### `==` vs `===`

`===` (strict equality) never coerces types — different types are always unequal. `==` (loose
equality) coerces one or both operands before comparing, following a notoriously confusing set
of rules:
```js
0 == '0'        // true  (string coerced to number)
0 == ''         // true  ('' coerced to 0)
0 == '  '       // true  (whitespace coerces to 0)
false == 'false' // false (!! surprising: 'false' coerces to NaN, not to false)
null == undefined // true (special case, only equal to each other)
NaN == NaN       // false (NaN is never equal to anything, including itself)
```
**Practical rule**: always use `===`/`!==` unless you have a specific, deliberate reason to
allow type coercion (the only common legitimate case is `if (x == null)` to check for both
`null` and `undefined` in one comparison). Interviewers frequently ask you to explain 3-4 of
the table rows above from memory — know the `NaN !== NaN` rule cold, it also explains why
`Number.isNaN()` exists and why `[NaN].includes(NaN)` is `true` while `[NaN].indexOf(NaN)` is
`-1` (indexOf uses `===` internally, `includes` uses the SameValueZero algorithm).

### Truthy / Falsy

Exactly 8 falsy values in JS, everything else is truthy: `false`, `0`, `-0`, `0n`, `""`,
`null`, `undefined`, `NaN`. Notably **`[]` and `{}` are truthy** (a very common gotcha —
`if ([])` runs the `if` branch).

## 4.2 Scope, Hoisting & the Temporal Dead Zone

```js
console.log(a); // undefined (not an error!) — var is hoisted, initialized as undefined
var a = 5;

console.log(b); // ReferenceError: Cannot access 'b' before initialization
let b = 10;      // let/const are hoisted too, but stay in the "Temporal Dead Zone" (TDZ)
                 // until their declaration line executes
```

- `var` is **function-scoped** (or globally scoped if outside a function), hoisted to the top
  of its scope and initialized to `undefined` immediately.
- `let`/`const` are **block-scoped** (`{ }` of any kind — if/for/while/bare blocks), hoisted
  but left uninitialized in the TDZ until their declaration statement runs.
- `const` doesn't mean "immutable value," it means "the binding (variable name) can't be
  reassigned." `const arr = [1,2]; arr.push(3);` is perfectly legal — you're mutating the
  object the binding points to, not reassigning the binding itself.

### Classic Closure-in-a-Loop Interview Question

```js
for (var i = 0; i < 3; i++) {
  setTimeout(() => console.log(i), 100);
}
// Prints: 3, 3, 3   (all three callbacks share the SAME `i`, which is 3 by the time they run)

for (let i = 0; i < 3; i++) {
  setTimeout(() => console.log(i), 100);
}
// Prints: 0, 1, 2   (let creates a NEW binding of `i` for each loop iteration)
```
This single example tests scope, closures, hoisting, and the event loop all at once — it's
one of the most reliable "does this person actually understand JS" interview probes. Be ready
to explain **why** `var` produces `3,3,3` (one shared function-scoped variable, mutated by the
loop, and all three closures capture a reference to that *same* variable, so by the time any
`setTimeout` callback runs — after the loop has already finished — they all read the final
value) and how to fix it with `var` if `let` weren't available: wrap the loop body in an IIFE
that captures the current value of `i` as a parameter.

## 4.3 Closures — The Concept Behind Half of JavaScript

> A closure is a function bundled together with references to its surrounding (lexical) scope
> — it "remembers" the variables from where it was defined, even after the outer function has
> returned.

```js
function makeCounter() {
  let count = 0; // private state, invisible from outside
  return {
    increment: () => ++count,
    decrement: () => --count,
    value: () => count,
  };
}
const counter = makeCounter();
counter.increment(); counter.increment();
console.log(counter.value()); // 2
// `count` cannot be accessed or mutated except through the returned methods —
// this is how JS achieves true "private" encapsulation before/without classes' # fields.
```

Practical closure use cases you should be able to produce on demand:
- **Data privacy / module pattern** (shown above).
- **Memoization**:
```js
function memoize(fn) {
  const cache = new Map();
  return (...args) => {
    const key = JSON.stringify(args);
    if (cache.has(key)) return cache.get(key);
    const result = fn(...args);
    cache.set(key, result);
    return result;
  };
}
```
- **Debounce/Throttle** (see Part 14 coding questions — always implemented via closures over a
  `timeoutId`/`lastCall` variable).
- **Partial application/currying**:
```js
const add = (a) => (b) => (c) => a + b + c;
add(1)(2)(3); // 6 — each returned arrow function closes over the previous argument(s)
```

Closures also cause the **only real "memory leak" risk that's actually about JS itself**: if a
long-lived closure (e.g., an event listener that's never removed) captures a reference to a
large object, that object can never be garbage collected as long as the closure exists —
covered more in 4.9.

## 4.4 `this`, `call`/`apply`/`bind`, and Arrow Functions

`this` in JavaScript is determined by **how a function is called**, not where it's defined
(except for arrow functions, which are the one exception):

```js
const obj = {
  name: 'Alice',
  regularFn() { console.log(this.name); },
  arrowFn: () => { console.log(this.name); },
};
obj.regularFn(); // "Alice" — called as obj.regularFn(), so `this` = obj
obj.arrowFn();   // undefined (or throws in strict mode/class fields) — arrow functions
                 // don't have their own `this`; they capture `this` from the ENCLOSING
                 // lexical scope at definition time (here, the module/global scope)

const detached = obj.regularFn;
detached(); // undefined — called with no receiver, `this` is undefined (strict mode)
            // or the global object (sloppy mode). This is the classic "losing this" bug
            // when passing a method as a callback, e.g. button.addEventListener('click', obj.regularFn)
```

**The four rules for determining `this`** (in priority order):
1. **`new` binding**: `new Fn()` → `this` is the newly created object.
2. **Explicit binding**: `fn.call(obj)`, `fn.apply(obj)`, `fn.bind(obj)()` → `this` is
   whatever you pass.
3. **Implicit binding**: `obj.method()` → `this` is `obj` (whatever is left of the dot at
   call time).
4. **Default binding**: plain `fn()` call → `this` is `undefined` (strict mode) or the global
   object (sloppy mode).
5. Arrow functions ignore all of the above — they inherit `this` lexically from where they
   were *written*, permanently, and cannot be rebound by `call`/`apply`/`bind`.

```js
function greet(greeting) { console.log(`${greeting}, ${this.name}`); }
const person = { name: 'Bob' };

greet.call(person, 'Hi');    // "Hi, Bob" — calls immediately with `this` = person
greet.apply(person, ['Hi']); // same as call, but args as an array
const bound = greet.bind(person); // returns a NEW function permanently bound to person
bound('Hey');                // "Hey, Bob"
```

**Why this matters in React specifically**: class component methods passed as event handlers
(`<button onClick={this.handleClick}>`) lose their `this` binding exactly like the `detached`
example above — this is precisely why older React code is full of `this.handleClick =
this.handleClick.bind(this)` in constructors, and precisely why arrow-function class fields
(`handleClick = () => {...}`) became popular (they capture `this` lexically once, at the
instance level, with no rebinding needed). Modern function components + hooks sidestep this
entire class of bug, which is one of several real reasons hooks were adopted so quickly (see
Part 7).

## 4.5 Prototypes & Classes

JavaScript's inheritance model is **prototypal**, not classical — every object has an internal
link (`[[Prototype]]`, exposed as `__proto__` or accessed via `Object.getPrototypeOf`) to
another object it delegates property lookups to when a property isn't found on itself.

```js
const animal = {
  speak() { console.log(`${this.name} makes a sound.`); }
};
const dog = Object.create(animal); // dog's prototype is `animal`
dog.name = 'Rex';
dog.speak(); // "Rex makes a sound." — `speak` isn't on `dog`, JS walks up the prototype chain
```

`class` syntax (ES6+) is **syntactic sugar** over this exact prototype mechanism — it doesn't
introduce a new inheritance model, just a cleaner syntax for it:

```js
class Animal {
  #internalId; // truly private field (# syntax), inaccessible from outside the class
  constructor(name) {
    this.name = name;
    this.#internalId = Math.random();
  }
  speak() { console.log(`${this.name} makes a sound.`); }
  static create(name) { return new Animal(name); } // static = called on the class itself
}
class Dog extends Animal {
  speak() {
    super.speak(); // call the parent's method
    console.log(`${this.name} barks.`);
  }
}
const d = new Dog('Rex');
d.speak();
// "Rex makes a sound."
// "Rex barks."
```
Under the hood: `Dog.prototype.__proto__ === Animal.prototype`, and instance methods
(`speak`) live on the prototype (shared across all instances, memory-efficient), while
instance fields set in the constructor (`this.name`) live on each individual object.

## 4.6 Functions Deep Dive

```js
// Function declaration — hoisted entirely (can call before its definition in source)
function add(a, b) { return a + b; }

// Function expression — NOT hoisted the same way (the variable is hoisted, the
// assignment is not), so calling before this line throws
const subtract = function (a, b) { return a - b; };

// Arrow function — no own `this`/`arguments`/`super`, cannot be used as a constructor
const multiply = (a, b) => a * b;

// Default parameters
function greet(name = 'stranger') { return `Hello, ${name}`; }

// Rest parameters — collects remaining args into a real array
function sum(...nums) { return nums.reduce((a, b) => a + b, 0); }

// IIFE (Immediately Invoked Function Expression) — creates an isolated scope, runs once
(function () {
  const privateVar = 'hidden from outer scope';
})();
```

### Higher-Order Functions

A function that takes a function as an argument and/or returns a function. This is the
foundation of `.map`/`.filter`/`.reduce`, middleware patterns, and React hooks/HOCs.

```js
const numbers = [1, 2, 3, 4, 5];
numbers.map(n => n * 2);              // [2,4,6,8,10] — transform each element
numbers.filter(n => n % 2 === 0);     // [2,4]        — keep matching elements
numbers.reduce((acc, n) => acc + n, 0); // 15          — fold into a single value
numbers.forEach(n => console.log(n)); // side effects only, returns undefined
numbers.find(n => n > 3);             // 4  — first match
numbers.some(n => n > 4);             // true — at least one matches
numbers.every(n => n > 0);            // true — all match
```
Know that `.map`/`.filter` return **new arrays** (never mutate the original — this
immutability is exactly what React relies on for cheap state-change detection), while `.sort`/
`.reverse`/`.splice`/`.push` mutate **in place** — a frequent React bug is calling `.sort()`
directly on state array (mutates it, React doesn't detect the change) instead of
`[...arr].sort()`.

## 4.7 Asynchronous JavaScript — Callbacks, Promises, Async/Await

JavaScript is **single-threaded** — one call stack, one thing executing at a time. Yet it
handles thousands of concurrent network requests, timers, and UI events without blocking.
The mechanism is the **event loop**, working together with Web APIs provided by the browser
(not the JS engine itself).

### The Event Loop, Call Stack, Task Queue & Microtask Queue

```
┌───────────────────────┐
│      Call Stack        │  ← synchronous code executes here, one frame at a time
└───────────────────────┘
            │
            ▼ (when stack is empty, event loop checks queues)
┌───────────────────────┐     ┌──────────────────────────┐
│  Microtask Queue        │ ←── Promise .then/.catch/.finally,
│  (drained FULLY first,  │     queueMicrotask, async/await continuations
│   before any macrotask) │
└───────────────────────┘
            │
            ▼
┌───────────────────────┐
│  Macrotask (Task) Queue │ ←── setTimeout, setInterval, DOM events, I/O,
│  (one task per loop tick)│     requestAnimationFrame (its own special queue)
└───────────────────────┘
```

**The single most important rule**: after every synchronous stack frame finishes, the engine
drains the **entire microtask queue** (running any promise callbacks queued so far, including
new ones added *while* draining) before it processes even a single macrotask (like a
`setTimeout` callback). This produces famously counter-intuitive ordering:

```js
console.log('1: sync start');

setTimeout(() => console.log('2: macrotask (setTimeout)'), 0);

Promise.resolve().then(() => console.log('3: microtask (promise)'));

console.log('4: sync end');

// Output order: 1, 4, 3, 2
// Even with setTimeout(..., 0), the promise microtask ALWAYS runs first,
// because ALL synchronous code finishes, THEN all microtasks drain, THEN the next macrotask.
```
This exact snippet (or a variant with multiple `setTimeout`s and `.then()`s) is one of the
most common "senior JS" interview questions — practice tracing through 3-4 variants until the
ordering is automatic, not something you have to reason through slowly.

### Callbacks & "Callback Hell"

```js
getUser(id, (user) => {
  getPosts(user.id, (posts) => {
    getComments(posts[0].id, (comments) => {
      console.log(comments); // deeply nested, hard to read, hard to error-handle
    }, onError);
  }, onError);
}, onError);
```
Promises were introduced specifically to flatten this pyramid and unify error handling.

### Promises

A `Promise` represents a value that will exist eventually — it's always in one of three
states: `pending` → `fulfilled` (resolved with a value) or `rejected` (failed with a reason),
and once settled, it never changes state again.

```js
function delay(ms, value) {
  return new Promise((resolve, reject) => {
    setTimeout(() => {
      if (value < 0) reject(new Error('negative value'));
      else resolve(value);
    }, ms);
  });
}

delay(1000, 42)
  .then(result => { console.log(result); return result * 2; }) // .then returns a NEW promise
  .then(doubled => console.log(doubled))
  .catch(err => console.error('caught:', err.message))
  .finally(() => console.log('always runs, success or failure'));
```

### Promise Combinators

| Method | Behavior |
|---|---|
| `Promise.all(promises)` | Resolves when **all** resolve (array of results); rejects **immediately** on the first rejection |
| `Promise.allSettled(promises)` | Always resolves, giving `{status, value/reason}` for every promise, never short-circuits |
| `Promise.race(promises)` | Settles as soon as the **first** promise settles (fulfilled or rejected) |
| `Promise.any(promises)` | Resolves as soon as the **first** promise fulfills; rejects only if ALL reject (with an AggregateError) |

```js
const [user, posts] = await Promise.all([fetchUser(), fetchPosts()]);
// Both requests fire in PARALLEL, not sequentially — huge, commonly-tested performance point:
// `await fetchUser(); await fetchPosts();` runs them one after another (slower);
// `Promise.all([fetchUser(), fetchPosts()])` starts both immediately, then waits for both.
```

### Async/Await — Syntactic Sugar Over Promises

```js
async function loadDashboard() {
  try {
    const user = await fetchUser();        // pauses HERE until the promise settles,
    const posts = await fetchPosts(user.id); // without blocking the rest of the app —
    return { user, posts };                  // other code/microtasks still run meanwhile
  } catch (err) {
    console.error('Failed to load dashboard:', err);
    throw err; // re-throw if the caller needs to know
  }
}
```
An `async` function **always returns a Promise**, even if you `return` a plain value (it gets
auto-wrapped). `await` can only be used inside an `async` function (or at the top level of
modern ES modules). `await` pauses that function's execution (not the whole program) until the
awaited promise settles, then resumes with the resolved value, or throws if it rejected —
which is why plain `try/catch` works for async errors when using `await`, but does **not**
catch errors inside a `.then()` chain without a matching `.catch()`.

### Common Async Pitfalls (frequently tested)

```js
// BUG: forEach does not wait for async callbacks — all three fetches "fire" but
// the function returns before any of them resolve, and any error is silently unhandled.
async function processAll(ids) {
  ids.forEach(async (id) => {
    await processItem(id);
  });
  console.log('done'); // logs BEFORE any processItem actually finishes
}

// FIX 1: sequential (one at a time, slower but ordered / rate-limited)
async function processAllSequential(ids) {
  for (const id of ids) {
    await processItem(id);
  }
}

// FIX 2: parallel (all at once, faster, use when order/rate doesn't matter)
async function processAllParallel(ids) {
  await Promise.all(ids.map(id => processItem(id)));
}
```

## 4.8 ES6+ Features You Must Know Fluently

```js
// Destructuring
const { name, age = 18, ...rest } = { name: 'Alice', city: 'NYC', job: 'Dev' };
const [first, , third] = [1, 2, 3]; // skip an element with a blank slot

// Swap without a temp variable
[a, b] = [b, a];

// Spread — expand an iterable into individual elements
const merged = { ...defaults, ...userOptions }; // shallow merge, later keys win
const combined = [...arr1, ...arr2];

// Template literals
const msg = `Hello ${name}, you are ${age} years old.`;

// Optional chaining & nullish coalescing
const city = user?.address?.city ?? 'Unknown'; // no error if address is null/undefined;
                                                 // ?? only falls back on null/undefined,
                                                 // NOT on 0/''/false (unlike ||)

const port = config.port ?? 3000;   // 0 is a valid port, so ?? is correct here
const portWrong = config.port || 3000; // BUG if config.port is legitimately 0

// Object shorthand & computed properties
const x = 1, y = 2;
const point = { x, y, [`label_${x}`]: 'origin' };

// Modules (ES Modules — the standard today)
// math.js
export const PI = 3.14159;
export default function square(n) { return n * n; }
// main.js
import square, { PI } from './math.js';
```

### Iterators & Generators

```js
function* range(start, end) {
  for (let i = start; i <= end; i++) yield i;
}
for (const n of range(1, 5)) console.log(n); // 1 2 3 4 5

// Generators power async iteration too (for-await-of over async generators),
// and are the mechanism libraries like Redux-Saga and Immer's patches build on.
```
Any object with a `Symbol.iterator` method works with `for...of`, spread syntax, and
destructuring — this is how `Array`, `String`, `Map`, `Set`, and `NodeList` all "just work"
with these syntaxes, and how you can make your own custom iterable classes.

## 4.9 Error Handling, Memory & Performance

```js
try {
  JSON.parse(invalidJson);
} catch (err) {
  if (err instanceof SyntaxError) console.error('Bad JSON:', err.message);
} finally {
  cleanup();
}

class ValidationError extends Error {
  constructor(message, field) {
    super(message);
    this.name = 'ValidationError';
    this.field = field;
  }
}
```

### Garbage Collection, In Brief

JS uses automatic memory management via **mark-and-sweep**: the engine periodically walks
from "roots" (global object, currently-executing call stack) and marks every object reachable
from them; anything unreachable gets swept (freed). The practical implication: **you cannot
leak memory just by "forgetting" a local variable** — it becomes unreachable and gets
collected. Real leaks in JS almost always come from something *external* keeping a reference
alive longer than intended:
- Event listeners added but never removed (`window.addEventListener` in a component that
  unmounts, without a matching `removeEventListener`).
- `setInterval` timers never cleared, holding closures alive forever.
- Detached DOM nodes still referenced by a JS variable/closure after being removed from the
  page.
- Global variables/caches (especially `Map`/objects used as caches) that grow unbounded
  without eviction.
- Closures over large objects captured by long-lived callbacks (see 4.3).

### Debounce & Throttle (canonical implementations, always closures)

```js
function debounce(fn, delay) {
  let timeoutId;
  return function (...args) {
    clearTimeout(timeoutId);
    timeoutId = setTimeout(() => fn.apply(this, args), delay);
  };
  // Use case: search-as-you-type — only fires `fn` after the user STOPS typing for `delay` ms
}

function throttle(fn, limit) {
  let inThrottle = false;
  return function (...args) {
    if (!inThrottle) {
      fn.apply(this, args);
      inThrottle = true;
      setTimeout(() => (inThrottle = false), limit);
    }
  };
  // Use case: scroll/resize handlers — guarantees `fn` runs at most once per `limit` ms
}
```
These two functions appear in essentially every frontend coding-round interview — know them
well enough to write from memory (full versions with edge cases like leading/trailing options
are in Part 14).

## 4.10 Design Patterns in JavaScript

- **Module Pattern**: IIFE or ES module exposing a small public API while keeping internals
  private (shown in 4.3).
- **Observer/Pub-Sub**: decouple event producers from consumers.
```js
class EventEmitter {
  #listeners = {};
  on(event, cb) { (this.#listeners[event] ??= []).push(cb); return this; }
  off(event, cb) { this.#listeners[event] = (this.#listeners[event] || []).filter(f => f !== cb); }
  emit(event, ...args) { (this.#listeners[event] || []).forEach(cb => cb(...args)); }
}
```
- **Singleton**: ensure only one instance exists (a module in ES Modules is already a
  singleton by nature, since imports are cached).
- **Factory**: a function that creates and returns objects without exposing `new`/class
  details to the caller.
- **Decorator**: wrap a function/object to add behavior without modifying the original (this
  is exactly what React Higher-Order Components and hooks like `useMemo` conceptually do).
- **Strategy**: pass in interchangeable algorithms as functions/objects
  (`array.sort(comparatorFn)` is a built-in example).

# Part 5 — TypeScript: Types That Actually Help You

TypeScript is a superset of JavaScript that adds a **structural, static type system**, checked
at compile time and erased completely before the code reaches a browser (types have zero
runtime cost/presence). It doesn't change how JS *behaves*, only catches an entire class of
bugs (`undefined is not a function`, typos in property names, wrong argument counts) before
you ever run the code.

## 5.1 Basic Types

```ts
let id: number = 42;
let name: string = 'Alice';
let isActive: boolean = true;
let tags: string[] = ['a', 'b'];
let tuple: [string, number] = ['age', 30]; // fixed-length, fixed-type-per-position array
let anything: any = 'avoid this — disables type checking entirely for this value';
let unknown_: unknown = fetchSomething(); // safer "any" — must narrow before use
let nothing: null = null;
let notDefined: undefined = undefined;
let neverReturns: never; // a function that always throws or infinite-loops returns `never`

function add(a: number, b: number): number {
  return a + b;
}

// Object type / interface
interface User {
  id: number;
  name: string;
  email?: string;      // optional property
  readonly createdAt: Date; // cannot be reassigned after creation
}

function greet(user: User): string {
  return `Hello, ${user.name}`;
}
```

### `any` vs `unknown` — a favorite interview question

`any` disables type checking entirely for that value — you can call any method, access any
property, assign it anywhere, with zero compiler complaints (and it "infects" anything it
touches). `unknown` is the type-safe counterpart: you can assign anything to it, but you
**cannot use it** until you narrow its type first (via `typeof`, `instanceof`, or a type
guard):

```ts
function processAny(val: any) {
  val.toUpperCase(); // compiles fine, may crash at runtime if val isn't a string
}
function processUnknown(val: unknown) {
  if (typeof val === 'string') {
    val.toUpperCase(); // OK — TypeScript has narrowed `val` to `string` inside this block
  }
}
```
**Rule of thumb given in every serious TS style guide**: never use `any` in application code
except as a deliberate, documented escape hatch; prefer `unknown` for genuinely-unknown
external data (API responses, JSON.parse results) and narrow it before use.

## 5.2 Interfaces vs Type Aliases

```ts
interface Point { x: number; y: number; }
type PointT = { x: number; y: number; };
```
Nearly interchangeable for object shapes, but:
- **`interface` can be re-opened/merged** — declaring `interface Point { z: number }` again
  later *adds* `z` to the same interface (declaration merging), useful for extending library
  types. `type` cannot be re-opened.
- **`type` can alias anything**: unions, primitives, tuples, mapped types — `interface`
  can only describe object/class shapes (plus function/constructor signatures).
```ts
type Status = 'idle' | 'loading' | 'success' | 'error'; // union — only `type` can do this
type ID = string | number;
```
- **`interface extends`** vs **`type` with `&` (intersection)** achieve similar composition:
```ts
interface Animal { name: string; }
interface Dog extends Animal { breed: string; }

type AnimalT = { name: string; };
type DogT = AnimalT & { breed: string; };
```
Practical guidance most style guides converge on: use `interface` for public object/class
shapes (especially library-facing APIs that might need extension), use `type` for unions,
tuples, and utility-type compositions.

## 5.3 Generics — Writing Reusable, Type-Safe Code

```ts
function identity<T>(value: T): T {
  return value;
}
const num = identity<number>(42);   // T = number, inferred even without explicit <number>
const str = identity('hello');      // T = string, inferred automatically

interface Box<T> {
  value: T;
}
const numberBox: Box<number> = { value: 5 };

function firstElement<T>(arr: T[]): T | undefined {
  return arr[0];
}

// Generic constraints — restrict T to types that have a certain shape
function getLength<T extends { length: number }>(item: T): number {
  return item.length; // safe — TS knows T has a .length property
}
getLength('hello');   // OK, strings have .length
getLength([1, 2, 3]); // OK, arrays have .length
// getLength(42);      // Error: number doesn't have .length
```
Generics are the mechanism behind `Array<T>`, `Promise<T>`, `Map<K, V>`, and virtually every
typed React hook (`useState<User | null>(null)`) — understanding them is non-negotiable for
any serious TypeScript+React work.

## 5.4 Utility Types (Built Into TypeScript)

| Utility | What it does |
|---|---|
| `Partial<T>` | Makes every property of `T` optional |
| `Required<T>` | Makes every property of `T` required (opposite of Partial) |
| `Readonly<T>` | Makes every property of `T` read-only |
| `Pick<T, K>` | Builds a type with only the keys `K` from `T` |
| `Omit<T, K>` | Builds a type with every key from `T` EXCEPT `K` |
| `Record<K, V>` | Builds an object type with keys `K` and values all of type `V` |
| `ReturnType<F>` | Extracts the return type of a function type `F` |
| `Parameters<F>` | Extracts the parameter tuple type of a function type `F` |
| `NonNullable<T>` | Removes `null`/`undefined` from a type |

```ts
interface User {
  id: number;
  name: string;
  email: string;
  password: string;
}

type PublicUser = Omit<User, 'password'>;         // { id, name, email }
type UserPreview = Pick<User, 'id' | 'name'>;      // { id, name }
type PartialUser = Partial<User>;                  // all fields optional — great for PATCH/update payloads
type UserMap = Record<number, User>;               // { [id: number]: User }

function createUser(): User { /* ... */ return {} as User; }
type CreateUserReturn = ReturnType<typeof createUser>; // User
```
These appear constantly in real codebases (`Omit<Props, 'onClick'>` to build a variant of a
component's props) and are frequently quizzed in interviews ("how would you make all fields of
an interface optional without rewriting it?" → `Partial<T>`).

## 5.5 Advanced Types — Conditional, Mapped, Template Literal

```ts
// Mapped type — transform every key of an existing type
type Nullable<T> = { [K in keyof T]: T[K] | null };

// Conditional type — a type-level "if" statement
type IsString<T> = T extends string ? true : false;
type A = IsString<'hi'>;  // true
type B = IsString<42>;    // false

// infer — extract a type from within another type
type ElementType<T> = T extends (infer U)[] ? U : never;
type Item = ElementType<string[]>; // string

// Template literal types — string manipulation at the TYPE level
type EventName = 'click' | 'hover' | 'focus';
type HandlerName = `on${Capitalize<EventName>}`;
// 'onClick' | 'onHover' | 'onFocus'
```
These are genuinely advanced and mostly used inside library/framework type definitions rather
than everyday app code — but senior/staff-level interviews at companies with heavy TS usage
(and library authors) do ask about `infer` and mapped types, so it's worth recognizing the
syntax even if you rarely write it yourself.

## 5.6 Enums & Literal Types

```ts
enum Direction { Up, Down, Left, Right } // numeric enum: Up=0, Down=1, ...
enum Status { Active = 'ACTIVE', Inactive = 'INACTIVE' } // string enum

// Increasingly preferred alternative — a "const object + union type" (no runtime enum
// object generated, tree-shakes better, and works identically with type narrowing):
const Status2 = { Active: 'ACTIVE', Inactive: 'INACTIVE' } as const;
type Status2 = typeof Status2[keyof typeof Status2]; // 'ACTIVE' | 'INACTIVE'
```

## 5.7 Type Narrowing & Type Guards

```ts
function printId(id: string | number) {
  if (typeof id === 'string') {
    console.log(id.toUpperCase()); // narrowed to string here
  } else {
    console.log(id.toFixed(2));    // narrowed to number here
  }
}

interface Cat { meow(): void; }
interface Dog { bark(): void; }
function isCat(animal: Cat | Dog): animal is Cat { // user-defined type guard
  return (animal as Cat).meow !== undefined;
}
function makeSound(animal: Cat | Dog) {
  if (isCat(animal)) animal.meow(); // narrowed to Cat
  else animal.bark();               // narrowed to Dog
}
```

## 5.8 TypeScript + React

```tsx
interface ButtonProps {
  label: string;
  onClick: () => void;
  variant?: 'primary' | 'secondary';
  children?: React.ReactNode;
}

function Button({ label, onClick, variant = 'primary', children }: ButtonProps) {
  return <button className={variant} onClick={onClick}>{label}{children}</button>;
}

// Typed hooks
const [count, setCount] = useState<number>(0);
const [user, setUser] = useState<User | null>(null);
const inputRef = useRef<HTMLInputElement>(null);

// Typed events
function handleChange(e: React.ChangeEvent<HTMLInputElement>) {
  console.log(e.target.value);
}
```
`React.ReactNode` is the broadest "renderable" type (strings, numbers, elements, fragments,
arrays of these, `null`/`undefined`/`boolean` which render as nothing) — use it for
`children`. Prefer explicit union types (`'primary' | 'secondary'`) over `string` for props
with a fixed set of valid values — this is what gives you autocomplete and compile-time typo
protection in JSX.

## 5.9 `tsconfig.json` Essentials

```json
{
  "compilerOptions": {
    "target": "ES2020",
    "module": "ESNext",
    "strict": true,
    "jsx": "react-jsx",
    "moduleResolution": "bundler",
    "esModuleInterop": true,
    "skipLibCheck": true,
    "noUnusedLocals": true,
    "noImplicitAny": true,
    "noUncheckedIndexedAccess": true
  }
}
```
- **`"strict": true`** turns on the full bundle of strict checks (`noImplicitAny`,
  `strictNullChecks`, `strictFunctionTypes`, etc.) — always enable this on new projects; it's
  the single setting with the highest bug-catching ROI.
- **`strictNullChecks`** (part of `strict`) is what makes `string | null` meaningfully
  different from `string` and forces you to handle the `null` case — without it, `null`/
  `undefined` are silently assignable to everything, defeating much of the type system's
  value.
- **`noUncheckedIndexedAccess`** makes `arr[i]` return `T | undefined` instead of just `T`,
  correctly reflecting that out-of-bounds access is possible — catches a surprisingly common
  class of real bugs, worth enabling even though it adds some `?.`/narrowing noise.

# Part 6 — The DOM, Browser APIs & the Rendering Pipeline

## 6.1 The DOM — A Live Tree, Not a Snapshot

The DOM (Document Object Model) is the browser's in-memory, object representation of your
HTML — and crucially, it's **live**: JavaScript can query it, mutate it, and the screen
updates to reflect those mutations, all without a network request.

```js
// Selecting elements
document.getElementById('app');
document.querySelector('.card');          // first match
document.querySelectorAll('.card');       // NodeList (all matches) — array-like, has forEach
                                           // but NOT map/filter/reduce directly (use Array.from first)

// Creating & inserting
const div = document.createElement('div');
div.className = 'card';
div.textContent = 'Hello'; // safe — sets text, does NOT parse HTML (no XSS risk)
div.innerHTML = '<b>Hello</b>'; // parses as HTML — DANGEROUS with untrusted input (XSS risk)
document.body.appendChild(div);
parentEl.insertBefore(div, referenceEl);
parentEl.replaceChild(newEl, oldEl);
el.remove(); // removes itself from the DOM

// Reading/writing attributes & classes
el.getAttribute('data-id');
el.setAttribute('aria-hidden', 'true');
el.classList.add('active');
el.classList.remove('active');
el.classList.toggle('active');
el.classList.contains('active');
```

**Security note**: `innerHTML` (and `insertAdjacentHTML`, `document.write`) parse the string
as real HTML — if that string contains untrusted user input, you've built a **stored/reflected
XSS vulnerability** the moment a malicious `<script>` or `onerror` attribute sneaks through.
Always prefer `textContent` for plain text, and if you must render user-supplied HTML,
sanitize it first with a vetted library (e.g., DOMPurify) — never hand-roll a regex-based
sanitizer. This exact question ("how would you safely render user-generated HTML content?")
is a standard frontend security interview probe.

## 6.2 Events — Bubbling, Capturing & Delegation

```js
el.addEventListener('click', (event) => {
  console.log(event.target);        // the actual element that was clicked
  console.log(event.currentTarget); // the element the listener is attached to
  event.stopPropagation();          // stop the event from bubbling further up
  event.preventDefault();           // stop the default browser action (e.g., link navigation, form submit)
}, { once: true, passive: true }); // options: fire only once; passive = never calls preventDefault (perf hint for scroll/touch listeners)
```

Events travel in three phases: **capturing** (top-down, root to target — opt in with
`{capture: true}`), **target** (the element itself), and **bubbling** (bottom-up, target back
to root — the default phase most listeners run in). This is why a click on a nested `<span>`
inside a `<button>` inside a `<div>` fires listeners on the `<span>`, then the `<button>`, then
the `<div>`, in that order, unless something calls `stopPropagation()`.

### Event Delegation — A Core Performance/Architecture Pattern

Instead of attaching a listener to every single list item (expensive with thousands of items,
and broken for items added later), attach **one** listener to a stable parent and inspect
`event.target`:

```js
document.getElementById('list').addEventListener('click', (event) => {
  const item = event.target.closest('.list-item'); // find nearest matching ancestor-or-self
  if (!item) return;
  console.log('Clicked item:', item.dataset.id);
});
```
This works because of event bubbling — a click on any descendant of `#list` bubbles up to
`#list`'s listener. Benefits: one listener regardless of list size, automatically works for
items added dynamically after the listener was attached (no re-binding needed). This is
*exactly* what React does internally (historically one root-level listener per event type,
now attached to the root DOM container) — understanding delegation demystifies "how does
React's event system work under the hood," a common React-internals interview question.

## 6.3 Fetch API & Networking

```js
async function getUser(id) {
  const res = await fetch(`/api/users/${id}`, {
    method: 'GET',
    headers: { 'Content-Type': 'application/json' },
    signal: AbortSignal.timeout(5000), // auto-abort after 5s
  });
  if (!res.ok) {
    throw new Error(`HTTP ${res.status}: ${res.statusText}`);
    // fetch does NOT reject on 4xx/5xx — only on network failure! Always check res.ok.
  }
  return res.json();
}

// Cancelling a request (e.g., user navigates away, or types a new search query)
const controller = new AbortController();
fetch('/api/search?q=term', { signal: controller.signal });
controller.abort(); // cancels the in-flight request
```
**The #1 fetch gotcha tested in interviews**: `fetch()`'s returned promise only rejects on
network-level failures (DNS failure, connection refused, CORS block) — a 404 or 500 response
is still a "successful" fetch from the API's point of view, resolving normally with
`res.ok === false`. Forgetting to check `res.ok` is one of the most common real-world bugs in
fetch-based code.

## 6.4 Storage APIs

| API | Persistence | Capacity | Sync/Async | Notes |
|---|---|---|---|---|
| `localStorage` | Survives browser restart, until cleared | ~5-10MB | Synchronous | Shared across all tabs/windows for the same origin |
| `sessionStorage` | Cleared when tab closes | ~5-10MB | Synchronous | Scoped per-tab, not shared |
| `Cookies` | Configurable expiry | ~4KB | Synchronous (via `document.cookie`, awkward API) | Sent with every matching HTTP request automatically — only storage the server can set/read natively |
| `IndexedDB` | Survives browser restart | Much larger (hundreds of MB+) | Asynchronous | Real transactional database in the browser, for structured/large data, offline apps |
| `Cache API` | Survives browser restart | Large | Asynchronous | Pairs with Service Workers for offline asset caching |

```js
localStorage.setItem('theme', 'dark');
localStorage.getItem('theme'); // 'dark'
localStorage.removeItem('theme');
localStorage.clear();
// Everything stored as STRINGS — objects must be serialized:
localStorage.setItem('user', JSON.stringify({ name: 'Alice' }));
const user = JSON.parse(localStorage.getItem('user'));
```
**Security note**: never store sensitive tokens (JWTs, session secrets) in `localStorage` if
you can avoid it — it's readable by any JS running on the page, making it directly vulnerable
to XSS-based theft. `httpOnly` cookies (inaccessible to JS entirely) are the safer default for
auth tokens; this exact tradeoff is a standard frontend security interview question.

## 6.5 The Browser Rendering Pipeline (Critical for Performance Understanding)

```
HTML  ──parse──▶  DOM Tree
CSS   ──parse──▶  CSSOM Tree
                       │
                       ▼
              DOM + CSSOM ──combine──▶ Render Tree (visible nodes + computed styles only)
                       │
                       ▼
                   Layout / Reflow  (compute exact size & position of every box)
                       │
                       ▼
                     Paint  (fill in pixels: text, colors, images, shadows, borders)
                       │
                       ▼
                   Composite  (layers combined by the GPU, produces final frame on screen)
```

- **Layout (reflow)** is triggered by anything that changes an element's geometry: width,
  height, margin, padding, position, font-size, adding/removing DOM nodes, even *reading*
  certain layout properties (`offsetWidth`, `getBoundingClientRect()`) forces a synchronous
  recalculation if styles were just changed ("layout thrashing" — see below).
- **Paint** is triggered by changes to visual-but-not-geometric properties: `color`,
  `background`, `box-shadow`, `border-radius` (without size change), `visibility`.
- **Composite-only** changes (the cheapest): `transform` and `opacity` — these can be handled
  entirely by the GPU compositor thread, skipping layout AND paint, which is *the* reason
  they're the gold standard for animation performance (see Part 3.6 and Part 8).

### Layout Thrashing — A Real Performance Bug Pattern

```js
// BAD: forces layout recalculation on EVERY iteration (read-write-read-write interleaved)
elements.forEach(el => {
  el.style.width = box.offsetWidth + 'px'; // WRITE (invalidates layout)
                                            // then next iteration's READ forces a synchronous
                                            // recalculation of the now-stale layout
});

// GOOD: batch all reads first, then all writes (avoids repeated forced synchronous layout)
const widths = elements.map(el => el.offsetWidth); // all READS first
elements.forEach((el, i) => { el.style.width = widths[i] + 'px'; }); // all WRITES after
```
This "batch reads, then batch writes" pattern (sometimes called FastDOM-style batching) is a
real technique senior frontend engineers are expected to know, and is directly testable via
the DevTools Performance tab (look for many small purple "Layout" blocks in a row — a
signature of thrashing).

## 6.6 Modern Observer APIs (Better Than Scroll/Resize Listeners)

```js
// IntersectionObserver — efficiently detect when an element enters/exits the viewport
// (or another element), WITHOUT expensive scroll-event polling + getBoundingClientRect calls
const observer = new IntersectionObserver((entries) => {
  entries.forEach(entry => {
    if (entry.isIntersecting) {
      entry.target.classList.add('visible'); // e.g., trigger a fade-in animation
      observer.unobserve(entry.target);       // stop watching once triggered, if one-shot
    }
  });
}, { threshold: 0.1, rootMargin: '0px 0px -50px 0px' });
document.querySelectorAll('.fade-in-section').forEach(el => observer.observe(el));

// ResizeObserver — react to an element's size changing (not just the viewport)
const resizeObserver = new ResizeObserver((entries) => {
  for (const entry of entries) {
    console.log('New size:', entry.contentRect.width, entry.contentRect.height);
  }
});
resizeObserver.observe(document.querySelector('.resizable-panel'));

// MutationObserver — react to DOM tree changes (added/removed nodes, attribute changes)
const mutationObserver = new MutationObserver((mutations) => {
  mutations.forEach(m => console.log(m.type, m.target));
});
mutationObserver.observe(document.body, { childList: true, subtree: true, attributes: true });
```
`IntersectionObserver` is the modern, GPU/compositor-friendly way to build **scroll-triggered
animations** and **infinite scroll/lazy-loading** — it runs asynchronously off the main
rendering path instead of firing on every scroll pixel like a naive `scroll` event listener
would, and is exactly what libraries like GSAP's ScrollTrigger use under the hood conceptually
(Part 8 covers ScrollTrigger's higher-level API built on these same browser primitives).

## 6.7 `requestAnimationFrame` — The Foundation of Smooth JS Animation

```js
let start;
function step(timestamp) {
  if (start === undefined) start = timestamp;
  const elapsed = timestamp - start;
  const progress = Math.min(elapsed / 1000, 1); // 0 to 1 over 1 second

  el.style.transform = `translateX(${progress * 300}px)`;

  if (progress < 1) {
    requestAnimationFrame(step); // schedule the NEXT frame
  }
}
requestAnimationFrame(step);
```
`requestAnimationFrame` (rAF) schedules a callback to run **right before the browser's next
repaint**, synced to the display's refresh rate (typically 60Hz = 60fps, but respects 120Hz+
displays too) — unlike `setTimeout`/`setInterval`, which are not synced to paint timing and can
easily cause dropped/uneven frames. Every serious JS animation library (GSAP included) uses
`requestAnimationFrame` internally as its core scheduling primitive; understanding this loop is
what separates "I can use GSAP" from "I understand what GSAP is actually doing for me," which
is exactly the depth Part 8 builds on.

## 6.8 Web Workers — True Parallelism

```js
// main.js
const worker = new Worker('worker.js');
worker.postMessage({ command: 'process', data: largeArray });
worker.onmessage = (e) => console.log('Result:', e.data);

// worker.js
self.onmessage = (e) => {
  const result = heavyComputation(e.data.data);
  self.postMessage(result);
};
```
Web Workers run JS on a genuinely separate OS thread with **no shared memory** (communication
is via message-passing/structured cloning, or `SharedArrayBuffer` for advanced cases) and
**no DOM access** — they exist specifically to move CPU-heavy work (image processing, large
data parsing/sorting) off the main thread so the UI never freezes, addressing the fact that
JS's main thread is otherwise single-threaded and blocking it blocks all rendering/interaction.

# Part 7 — React: Components, Hooks, State, Performance, Ecosystem

## 7.1 What React Actually Is

React is a JavaScript library for building UI out of composable **components** — functions
that take data (`props`) and return a description of what should appear on screen, written in
**JSX** (a syntax extension that looks like HTML but compiles to plain JS function calls).
React's core job is to keep the DOM in sync with your data automatically, using a **virtual
DOM diffing** algorithm so it never asks you to manually call `document.createElement`/
`appendChild`.

```jsx
function Greeting({ name }) {
  return <h1>Hello, {name}!</h1>;
}
// Babel/SWC compiles this JSX to:
// return React.createElement('h1', null, 'Hello, ', name, '!');
// (modern React uses the newer jsx-runtime, but the concept is identical:
//  JSX is just sugar for function calls that build a tree of plain JS objects)
```

### The Virtual DOM & Reconciliation, Briefly

Every render, a component returns a lightweight JS object tree (the "virtual DOM") describing
the desired UI. React compares (**diffs**) this new tree against the previous one
(**reconciliation**) and computes the minimal set of real DOM mutations needed, then applies
them in a batch. This is faster than naively re-rendering the entire real DOM on every change,
and — more importantly for developer experience — it lets you write UI as "here's what the
screen should look like given this data" (declarative) instead of "here's the exact sequence
of DOM calls to get from the old state to the new state" (imperative).

## 7.2 Components, Props & Composition

```jsx
function Card({ title, children }) {
  return (
    <div className="card">
      <h2>{title}</h2>
      <div className="card-body">{children}</div>
    </div>
  );
}
function App() {
  return (
    <Card title="Welcome">
      <p>This is passed as `children`.</p>
    </Card>
  );
}
```
Props are **read-only** from the receiving component's perspective — a component must never
mutate its own props; data flows **one way, down** the tree ("unidirectional data flow"). To
send data back "up," a parent passes a callback function down as a prop, and the child calls
it (this is the entire mechanism behind every "controlled input" and "lift state up" pattern).

## 7.3 State — `useState`

```jsx
function Counter() {
  const [count, setCount] = useState(0);
  return (
    <div>
      <p>Count: {count}</p>
      <button onClick={() => setCount(count + 1)}>+1</button>
      <button onClick={() => setCount(prev => prev + 1)}>+1 (functional update)</button>
    </div>
  );
}
```
**Functional updates (`setCount(prev => prev + 1)`) vs direct updates (`setCount(count + 1)`)**
— a classic interview distinction: state updates inside React are **asynchronous and
batched**, so if you call `setCount(count + 1)` twice in the same event handler, both calls
close over the *same* stale `count` value from that render, and you only get +1 total, not +2.
The functional form always receives the latest pending state, so calling it twice correctly
produces +2:
```jsx
function handleClick() {
  setCount(count + 1); // both reference the SAME `count` from this render
  setCount(count + 1); // net effect: +1, not +2 (surprising to beginners)
}
function handleClickFixed() {
  setCount(prev => prev + 1); // uses latest pending state
  setCount(prev => prev + 1); // net effect: +2, correct
}
```
**State updates never mutate in place** — always create new objects/arrays:
```jsx
// WRONG — mutates state directly, React won't detect the change (same reference)
function addTodoWrong(text) {
  todos.push({ text, done: false });
  setTodos(todos);
}
// RIGHT — creates a new array, React sees a new reference and re-renders
function addTodoRight(text) {
  setTodos([...todos, { text, done: false }]);
}
```

## 7.4 Side Effects — `useEffect`

```jsx
useEffect(() => {
  const controller = new AbortController();
  fetch(`/api/users/${userId}`, { signal: controller.signal })
    .then(res => res.json())
    .then(setUser)
    .catch(err => { if (err.name !== 'AbortError') console.error(err); });

  return () => controller.abort(); // CLEANUP — runs before the next effect, and on unmount
}, [userId]); // dependency array — effect re-runs ONLY when userId changes
```
The dependency array is the single most misunderstood part of `useEffect`:
- **Omitted entirely** (`useEffect(() => {...})`): runs after **every** render.
- **`[]` (empty array)**: runs **once**, after the initial mount only.
- **`[userId]`**: runs after mount, and again any time `userId` changes between renders
  (compared via `Object.is`, i.e. reference equality for objects/arrays).
- The **cleanup function** (the function you `return` from the effect) runs right before the
  effect runs again, and once more when the component unmounts — this is where you cancel
  subscriptions, clear timers, remove event listeners, and abort in-flight requests to avoid
  the classic "Can't perform a React state update on an unmounted component" warning and real
  memory leaks (Part 4.9's leak list applies directly inside `useEffect`).

**The exhaustive-deps rule**: every reactive value (props, state, or anything derived from
them) that your effect *reads* should be listed in the dependency array — the official
`eslint-plugin-react-hooks` enforces this and its warnings should almost never be silenced,
because omitting a dependency is the #1 source of "stale closure" bugs (the effect capturing
an old value of a prop/state variable forever).

## 7.5 The Rest of the Core Hooks

```jsx
// useRef — a mutable box that persists across renders WITHOUT causing a re-render when
// changed (unlike state). Two main uses: (1) DOM element references, (2) any mutable
// value you need to keep around between renders that shouldn't trigger a re-render.
function TextInputWithFocusButton() {
  const inputRef = useRef(null);
  return (
    <>
      <input ref={inputRef} />
      <button onClick={() => inputRef.current.focus()}>Focus the input</button>
    </>
  );
}

// useContext — read a value provided higher up the tree, without prop-drilling through
// every intermediate component
const ThemeContext = createContext('light');
function App() {
  return (
    <ThemeContext.Provider value="dark">
      <Toolbar />
    </ThemeContext.Provider>
  );
}
function Toolbar() {
  const theme = useContext(ThemeContext); // 'dark' — no props needed in between
  return <div className={theme}>...</div>;
}

// useReducer — for state logic more complex than a simple useState (multiple sub-values
// that update together, or state transitions that depend on the previous state in
// non-trivial ways) — same underlying model as Redux, scoped to one component
function reducer(state, action) {
  switch (action.type) {
    case 'increment': return { count: state.count + 1 };
    case 'decrement': return { count: state.count - 1 };
    case 'reset': return { count: 0 };
    default: throw new Error(`Unknown action: ${action.type}`);
  }
}
function Counter() {
  const [state, dispatch] = useReducer(reducer, { count: 0 });
  return (
    <>
      <p>{state.count}</p>
      <button onClick={() => dispatch({ type: 'increment' })}>+</button>
      <button onClick={() => dispatch({ type: 'decrement' })}>-</button>
    </>
  );
}

// useMemo — memoize an EXPENSIVE COMPUTATION so it doesn't re-run on every render unless
// its dependencies change
const sortedList = useMemo(() => expensiveSort(items), [items]);

// useCallback — memoize a FUNCTION REFERENCE so it doesn't change identity on every render
// (critical when passing callbacks to memoized children, or as a dependency of another
// hook's dependency array)
const handleClick = useCallback(() => {
  doSomething(id);
}, [id]);

// useLayoutEffect — like useEffect, but fires SYNCHRONOUSLY after DOM mutations, before
// the browser paints — use only when you need to measure/mutate the DOM before the user
// sees a flash of the "wrong" layout (e.g., measuring an element's size to position a
// tooltip). Blocks painting, so use sparingly — useEffect is the right default 95% of the time.

// useId — generates a stable, unique ID for accessibility attributes (linking a label to
// an input) that's consistent between server and client renders (important for SSR/hydration)
const id = useId();
```

### `useMemo`/`useCallback` — When Do You Actually Need Them?

A common misconception is "wrap everything in `useMemo`/`useCallback` for performance." In
reality, they have their own (small) cost, and are only worth it when: (1) the computation is
genuinely expensive, or (2) you need **referential stability** to avoid breaking `React.memo`
on a child component or avoid re-triggering another hook's effect. Reaching for them
reflexively on every function/value is a common **anti-pattern** senior reviewers push back on
— profile first, memoize second.

## 7.6 Custom Hooks — Extracting Reusable Stateful Logic

```jsx
function useLocalStorage(key, initialValue) {
  const [value, setValue] = useState(() => {
    try {
      const stored = localStorage.getItem(key);
      return stored ? JSON.parse(stored) : initialValue;
    } catch {
      return initialValue;
    }
  });
  useEffect(() => {
    localStorage.setItem(key, JSON.stringify(value));
  }, [key, value]);
  return [value, setValue];
}

function usePrevious(value) {
  const ref = useRef();
  useEffect(() => { ref.current = value; }, [value]);
  return ref.current; // returns the value from the PREVIOUS render
}

function useDebounce(value, delay) {
  const [debounced, setDebounced] = useState(value);
  useEffect(() => {
    const timer = setTimeout(() => setDebounced(value), delay);
    return () => clearTimeout(timer);
  }, [value, delay]);
  return debounced;
}
```
A custom hook is just a JS function whose name starts with `use` and which calls other hooks
internally — it's the primary mechanism for sharing **stateful logic** between components
(as opposed to Higher-Order Components or render props, the older patterns this replaced).
The **Rules of Hooks** (enforced by `eslint-plugin-react-hooks`) exist so React can correctly
associate each hook call with its own persistent state slot across renders:
1. Only call hooks at the **top level** — never inside loops, conditions, or nested
   functions (this would change the *order* of hook calls between renders, corrupting
   React's internal bookkeeping, which relies on call order, not names).
2. Only call hooks from **React function components** or **other custom hooks** — never from
   regular JS functions.

## 7.7 Rendering Behavior & Performance Optimization

### Why Does a Component Re-render?

A React component re-renders when: (1) its own state changes, (2) its parent re-renders (by
default, **every** child re-renders when a parent re-renders, regardless of whether the
child's own props changed), or (3) a context value it consumes changes. This "parent
re-renders → all children re-render" default is the root cause of most React performance
problems in practice, and the entire reason `React.memo`/`useMemo`/`useCallback` exist.

```jsx
const ExpensiveChild = React.memo(function ExpensiveChild({ data }) {
  console.log('ExpensiveChild rendered');
  return <div>{data}</div>;
});
// React.memo does a SHALLOW comparison of props before deciding to skip a re-render.
// If `data` is a new object/array reference every render (even with identical content),
// memo won't help — this is exactly why useMemo/useCallback matter for props passed
// to memoized children.
```

### Keys — Why They Matter So Much

```jsx
{items.map(item => <ListItem key={item.id} {...item} />)}
```
`key` tells React's reconciler **which array item is which** across renders, so it can
correctly match up existing DOM nodes/component state instead of destroying and recreating
everything. Using the **array index** as a key is a classic anti-pattern when the list can be
reordered, filtered, or have items inserted/removed from the middle — React will
mis-associate state (e.g., an input's typed text "jumping" to the wrong row) because the index
no longer reliably identifies the same logical item across renders. Always use a stable,
unique ID from your data; only fall back to index for lists that are static and never
reordered/filtered.

### Virtualization — Rendering Only What's Visible

For lists with thousands of items, rendering every single DOM node is wasteful even with
perfect memoization. **List virtualization** (via libraries like `react-window` or
`react-virtual`/TanStack Virtual) renders only the items currently visible in the viewport
(plus a small buffer), recycling DOM nodes as the user scrolls — turning an O(n) DOM cost into
roughly O(viewport size), regardless of total list length. This is a standard answer to "how
would you render a list of 100,000 rows performantly?" in system design interviews (Part 13).

### `React.lazy` & Code Splitting

```jsx
const Settings = React.lazy(() => import('./Settings'));
function App() {
  return (
    <Suspense fallback={<Spinner />}>
      <Settings />
    </Suspense>
  );
}
```
`React.lazy` + dynamic `import()` splits a component into its own JS chunk, downloaded only
when it's actually rendered — reducing the initial bundle size for routes/features not every
user visits (e.g., an admin settings panel). `<Suspense>` shows a fallback UI while the chunk
loads.

## 7.8 Context — Patterns & Pitfalls

```jsx
const AuthContext = createContext(null);

function AuthProvider({ children }) {
  const [user, setUser] = useState(null);
  const login = useCallback(async (credentials) => {
    const u = await api.login(credentials);
    setUser(u);
  }, []);
  const value = useMemo(() => ({ user, login }), [user, login]);
  // ^ memoizing the context value is IMPORTANT: without it, a new `{ user, login }` object
  // is created every render of AuthProvider, and EVERY consumer re-renders every time,
  // even if `user` itself didn't change.
  return <AuthContext.Provider value={value}>{children}</AuthContext.Provider>;
}
function useAuth() {
  const ctx = useContext(AuthContext);
  if (!ctx) throw new Error('useAuth must be used within AuthProvider');
  return ctx;
}
```
**Context is not a general state-management replacement for Redux/Zustand** — every consumer
of a context re-renders whenever the context value changes, with no built-in mechanism to
subscribe to just a slice of it (unlike Redux's selector-based subscriptions). Context is best
for genuinely global, infrequently-changing values (theme, current user, locale/i18n) — for
frequently-updating, granular app state, a dedicated state library or splitting context into
smaller, more targeted providers is the better answer, and is a common senior-interview
follow-up to "when would you use Context vs Redux?"

## 7.9 Forms in React

```jsx
function LoginForm() {
  const [email, setEmail] = useState('');
  const [password, setPassword] = useState('');
  const [errors, setErrors] = useState({});

  function handleSubmit(e) {
    e.preventDefault();
    const newErrors = {};
    if (!email.includes('@')) newErrors.email = 'Invalid email';
    if (password.length < 8) newErrors.password = 'Too short';
    setErrors(newErrors);
    if (Object.keys(newErrors).length === 0) {
      submitLogin({ email, password });
    }
  }

  return (
    <form onSubmit={handleSubmit}>
      <input
        type="email"
        value={email}                         // "controlled" — React state is the single
        onChange={e => setEmail(e.target.value)} // source of truth for the input's value
      />
      {errors.email && <span role="alert">{errors.email}</span>}
      <input type="password" value={password} onChange={e => setPassword(e.target.value)} />
      <button type="submit">Log in</button>
    </form>
  );
}
```
**Controlled vs uncontrolled inputs**: a *controlled* input's `value` is driven entirely by
React state (as above) — React re-renders the input on every keystroke with the new value,
giving you full control (validation, formatting, conditional disabling) at the cost of a
re-render per keystroke. An *uncontrolled* input lets the DOM manage its own value natively;
you read it only when needed via a `ref`:
```jsx
function UncontrolledForm() {
  const emailRef = useRef();
  function handleSubmit(e) {
    e.preventDefault();
    console.log(emailRef.current.value); // read directly from the DOM on submit
  }
  return <form onSubmit={handleSubmit}><input ref={emailRef} defaultValue="" /></form>;
}
```
For large/complex forms, libraries like React Hook Form use uncontrolled inputs internally
(subscribing to changes via refs rather than re-rendering on every keystroke) specifically to
sidestep the re-render cost of fully controlled forms at scale — a real performance
consideration worth citing in interviews.

## 7.10 Error Boundaries

```jsx
class ErrorBoundary extends React.Component {
  state = { hasError: false };
  static getDerivedStateFromError(error) {
    return { hasError: true };
  }
  componentDidCatch(error, info) {
    logErrorToService(error, info);
  }
  render() {
    if (this.state.hasError) return <h2>Something went wrong.</h2>;
    return this.props.children;
  }
}
```
Error boundaries **must** be class components (there is no hook equivalent as of React's
stable API — `getDerivedStateFromError`/`componentDidCatch` have no function-component
counterpart) and only catch errors during **rendering**, in lifecycle methods, and in
constructors of the component tree below them — they do **not** catch errors in event
handlers (use a plain `try/catch` there instead), async code, or server-side rendering.

## 7.11 React Router (Client-Side Routing) Essentials

```jsx
import { createBrowserRouter, RouterProvider, Link, useParams, useNavigate } from 'react-router-dom';

const router = createBrowserRouter([
  { path: '/', element: <Home /> },
  { path: '/users/:id', element: <UserProfile /> },
  { path: '*', element: <NotFound /> },
]);
function App() { return <RouterProvider router={router} />; }

function UserProfile() {
  const { id } = useParams();          // read route params
  const navigate = useNavigate();      // programmatic navigation
  return (
    <div>
      <p>Viewing user {id}</p>
      <button onClick={() => navigate(-1)}>Back</button>
      <Link to="/">Home</Link>          {/* NOT <a href>! avoids a full page reload */}
    </div>
  );
}
```
`<Link>` intercepts the click and updates the URL via the browser's History API
(`pushState`), then React Router re-renders just the matched route's component — no full page
navigation/reload, preserving the SPA experience. This is the client-side-routing analog of
`e.preventDefault()` on forms (Part 2.4) — both intercept a default browser navigation to keep
control inside the JS app.

## 7.12 SSR & Next.js Basics (Conceptual)

Next.js layers file-system-based routing, SSR/SSG/ISR, and API routes on top of React. Key
concepts:
- **Server Components (React Server Components / RSC)**: components that render **only** on
  the server, ship **zero JS** to the client for that component's own code, and can directly
  `await` data (database calls, file reads) inside the component body — no `useEffect`
  fetching dance needed. They cannot use state/effects/browser APIs.
- **Client Components** (`'use client'` directive): the "classic" React components we've
  covered all Part 7 — interactive, stateful, hydrated in the browser.
- **Hydration**: the server sends fully-rendered HTML; React then "hydrates" it in the
  browser — attaching event listeners and internal state to the *existing* DOM nodes rather
  than re-creating them, so the user sees content immediately (fast First Contentful Paint)
  while JS loads in the background for interactivity.
- **Hydration mismatch errors** happen when server-rendered HTML doesn't exactly match what
  the client would render on first pass (common causes: using `Date.now()`/`Math.random()`
  directly in render, or checking `typeof window !== 'undefined'` inconsistently) — a
  frequently-asked "debug this" style interview question at companies using Next.js/SSR
  heavily.

## 7.13 Testing React with React Testing Library (preview — full detail in Part 10)

```jsx
import { render, screen, fireEvent } from '@testing-library/react';

test('increments count on button click', () => {
  render(<Counter />);
  const button = screen.getByRole('button', { name: /\+1/i });
  fireEvent.click(button);
  expect(screen.getByText('Count: 1')).toBeInTheDocument();
});
```
React Testing Library's guiding philosophy — "test components the way a user actually uses
them" (query by visible text/role/label, not by internal implementation details like state
variable names or CSS classes) — is itself a common interview discussion point (see Part 10
and Part 14).

## 7.14 State Management Ecosystem — Redux, Zustand & When You Need Them

**Do you even need a state library?** For most apps, `useState`/`useReducer` + Context covers
you fine. Reach for a dedicated library when: state is genuinely shared across many unrelated
parts of the tree, updates are frequent and Context's "every consumer re-renders" cost becomes
a real problem, or you need powerful devtools (time-travel debugging, action logs) for complex
state transitions.

### Redux (with Redux Toolkit — the modern standard way to write it)

```js
import { createSlice, configureStore } from '@reduxjs/toolkit';

const counterSlice = createSlice({
  name: 'counter',
  initialState: { value: 0 },
  reducers: {
    incremented: (state) => { state.value += 1; }, // looks like mutation, but Redux
                                                     // Toolkit uses Immer internally to
                                                     // produce an immutable update safely
    decremented: (state) => { state.value -= 1; },
    addAmount: (state, action) => { state.value += action.payload; },
  },
});
export const { incremented, decremented, addAmount } = counterSlice.actions;
const store = configureStore({ reducer: { counter: counterSlice.reducer } });

// In a component:
import { useSelector, useDispatch } from 'react-redux';
function Counter() {
  const count = useSelector(state => state.counter.value); // subscribes to JUST this slice —
                                                              // re-renders only when `.value` changes,
                                                              // not on unrelated state changes elsewhere
  const dispatch = useDispatch();
  return <button onClick={() => dispatch(incremented())}>{count}</button>;
}
```
Redux's core model: a single, centralized store; state changes only via dispatched **actions**
(plain objects describing "what happened"); **reducers** are pure functions
`(state, action) => newState` describing how state transitions; and **selectors**
(`useSelector`) let each component subscribe to only the slice of state it needs, avoiding
Context's "re-render every consumer" problem.

### Zustand — A Minimal Alternative

```js
import { create } from 'zustand';

const useStore = create((set) => ({
  count: 0,
  increment: () => set((state) => ({ count: state.count + 1 })),
  reset: () => set({ count: 0 }),
}));

function Counter() {
  const count = useStore((state) => state.count); // selector — only re-renders on `count` changes
  const increment = useStore((state) => state.increment);
  return <button onClick={increment}>{count}</button>;
}
```
Zustand achieves the same "selector-based, no-unnecessary-re-render" subscription model as
Redux with drastically less boilerplate (no actions/reducers/providers required) — a common
modern interview discussion is "Redux vs Zustand vs Context, when would you pick each?" The
honest answer: Context for simple/rarely-changing global values, Zustand for most apps needing
real shared state with minimal ceremony, Redux (Toolkit) for large teams/codebases that
specifically benefit from its strict conventions, middleware ecosystem, and time-travel
devtools.

### TanStack Query (React Query) — Server State Is Different From Client State

A frequently-tested distinction: **client state** (UI toggles, form inputs, current tab) is
owned entirely by your app. **Server state** (data fetched from an API) is owned by the
server, can go stale, can be requested by multiple components, and needs caching/
revalidation/loading-and-error states — using `useState`/Redux to manually manage all of this
(loading flags, error flags, manual refetching, cache invalidation) is exactly the boilerplate
TanStack Query (and SWR) exist to eliminate:
```jsx
import { useQuery } from '@tanstack/react-query';
function UserProfile({ userId }) {
  const { data, isLoading, error } = useQuery({
    queryKey: ['user', userId],
    queryFn: () => fetch(`/api/users/${userId}`).then(r => r.json()),
    staleTime: 60_000, // consider cached data fresh for 60s before refetching
  });
  if (isLoading) return <Spinner />;
  if (error) return <ErrorMessage error={error} />;
  return <div>{data.name}</div>;
}
```
Being able to articulate "client state vs server state, and why you'd reach for React
Query/SWR instead of jamming fetched data into Redux/useState directly" is a strong signal in
mid-to-senior React interviews.

---

# Part 8 — Animation Deep Dive: CSS, GSAP, ScrollTrigger, Framer Motion, FLIP, 60fps Discipline

This part is written for genuinely "tinkering" with animation — not just copy-pasting a tween,
but understanding *why* an animation feels good or janky, how to sequence complex timelines,
and how to debug performance problems in DevTools. Read Part 3.6 (transform/opacity
performance) and Part 6.5 (rendering pipeline) first if you haven't — everything here builds
directly on those foundations.

## 8.1 The Animation Decision Tree

| If you need... | Reach for... |
|---|---|
| A simple hover/focus state change, a spinner, a one-shot entrance | **CSS transitions/keyframes** (Part 3.6/3.7) — free, GPU-accelerated, no JS needed |
| Sequenced, interruptible, or scroll-driven animation; precise easing/timing control; staggering many elements | **GSAP** |
| Animating React component mount/unmount, layout changes, gesture-driven UI (drag, swipe) idiomatically within React's model | **Framer Motion** |
| Animating SVG paths being "drawn," morphing shapes | **GSAP (DrawSVG/MorphSVG plugins) or CSS `stroke-dasharray` tricks** |
| Complex physics (springs, inertia, collisions) | **GSAP's physics plugins, Framer Motion springs, or a dedicated physics lib (Matter.js) for true simulation** |

## 8.2 Why JavaScript-Driven Animation Sometimes Beats CSS

CSS animations are declarative and great for simple, self-contained effects, but they fall
short when you need to: **sequence** many elements with precise relative timing ("animate A,
then 0.2s later start B while A is still finishing"), **interrupt and reverse** an in-progress
animation smoothly (CSS handles this awkwardly), **dynamically compute** target values from
JS data, or **synchronize with scroll position/user input** frame-by-frame. GSAP (GreenSock
Animation Platform) is the industry-standard JS animation library precisely because it solves
all of these while still ultimately animating `transform`/`opacity` under the hood for
performance (it does NOT bypass the rendering pipeline rules from Part 3.6 — it's simply a
much more powerful and ergonomic API for *driving* those same GPU-friendly properties, plus it
can animate things CSS can't, like arbitrary JS object properties, canvas/WebGL values, or
SVG attributes).

## 8.3 GSAP Core — Tweens

```bash
npm install gsap
```

```js
import { gsap } from 'gsap';

// gsap.to() — animate FROM the current/CSS state TO the given values
gsap.to('.box', {
  x: 300,           // translateX(300px) — GSAP understands plain x/y as transforms automatically
  rotation: 360,    // degrees
  scale: 1.5,
  duration: 1.2,
  ease: 'power2.out',
  delay: 0.2,
  onComplete: () => console.log('done!'),
});

// gsap.from() — animate FROM the given values TO the current/CSS state (great for entrances)
gsap.from('.card', { y: 50, opacity: 0, duration: 0.6, stagger: 0.1 });

// gsap.fromTo() — explicit control over BOTH start and end state (most predictable/safe)
gsap.fromTo('.modal',
  { opacity: 0, scale: 0.9 },              // from
  { opacity: 1, scale: 1, duration: 0.3 }  // to
);

// gsap.set() — instantly apply values with NO animation (useful for setting up initial state)
gsap.set('.box', { opacity: 0 });
```
**Why `fromTo` is often the safest choice in real projects**: `gsap.from()` reads the
element's *current* computed styles as the "to" state — if a previous animation, a CSS class,
or a race condition already changed those styles, `.from()` can produce inconsistent results.
`fromTo()` makes both ends of the animation fully explicit and reproducible, which matters a
lot once animations are triggered conditionally (e.g., on route change, in React effects).

GSAP accepts any valid CSS selector string, a DOM element, a NodeList/array of elements, or
(in React) a ref's `.current` — and can animate virtually any numeric property: `x`/`y`
(translate), `rotation`, `scale`/`scaleX`/`scaleY`, `opacity`, `width`/`height` (works, but
remember Part 3.6/6.5 — animating these still triggers layout, so prefer `scale` for size
changes where visually acceptable), CSS custom properties, SVG attributes, even arbitrary
plain JS object properties (useful for animating a counter number or a canvas draw progress).

## 8.4 GSAP Timelines — Sequencing Multiple Animations

A `Timeline` is GSAP's sequencing tool — a container of tweens with a shared, controllable
playhead, so you can play/pause/reverse/scrub the *entire sequence* as one unit instead of
juggling `setTimeout` chains or nested `onComplete` callbacks.

```js
const tl = gsap.timeline({ defaults: { duration: 0.5, ease: 'power2.out' } });

tl.to('.title', { opacity: 1, y: 0 })
  .to('.subtitle', { opacity: 1, y: 0 }, '-=0.3')   // start 0.3s BEFORE the previous ends (overlap)
  .to('.button', { opacity: 1, scale: 1 }, '+=0.1') // start 0.1s AFTER the previous ends (gap)
  .to('.decoration', { rotation: 360 }, '<')        // start at the SAME TIME as the previous tween started
  .to('.footer', { opacity: 1 }, 'footerLabel');    // position can also be a LABEL string

tl.addLabel('footerLabel', 1.5); // named position, referenceable from anywhere in the timeline

// Controlling the whole sequence:
tl.pause();
tl.play();
tl.reverse();      // plays the ENTIRE sequence backwards, correctly
tl.seek(1.2);       // jump to a specific time
tl.timeScale(2);    // play at 2x speed
tl.progress(0.5);   // jump to 50% through the timeline (great for scrubbing, see ScrollTrigger)
```

### The Position Parameter — GSAP's Most Powerful, Most Under-Used Feature

The optional third argument to `.to()`/`.from()`/`.fromTo()` inside a timeline controls
**when** that tween starts relative to the timeline (not relative to the previous tween's
start, by default — relative to its *end*):

| Position value | Meaning |
|---|---|
| (omitted) | Starts right after the previous tween ends (sequential, the default) |
| `"+=0.5"` | Starts 0.5s after the previous tween ends (adds a gap) |
| `"-=0.3"` | Starts 0.3s before the previous tween ends (creates overlap) |
| `"<"` | Starts at the same time the **previous** tween started |
| `">"` | Starts at the same time the **previous** tween ended (same as default) |
| `"myLabel"` | Starts at an explicitly named label |
| `1.5` (a number) | Starts at an absolute time (in seconds) from the timeline's start |

Mastering the position parameter is what separates "I can make one thing move" from "I can
choreograph a whole page's entrance sequence with natural-feeling overlaps" — practice
building a simple hero-section entrance (headline, then subtext overlapping slightly, then a
CTA button popping in after) purely with position parameters, no `setTimeout` anywhere.

## 8.5 Easing & Stagger

**Easing** describes the *rate of change* of an animation over time — linear motion (constant
speed) reads as robotic/artificial to the human eye; real-world motion accelerates and
decelerates, which is exactly what easing curves simulate.

```js
gsap.to('.box', { x: 300, ease: 'power2.out' });   // fast start, slow finish — great for entrances
gsap.to('.box', { x: 300, ease: 'power2.in' });     // slow start, fast finish — great for exits
gsap.to('.box', { x: 300, ease: 'power2.inOut' });  // slow-fast-slow — great for looping/continuous motion
gsap.to('.box', { x: 300, ease: 'back.out(1.7)' }); // overshoots then settles — playful, "bouncy" feel
gsap.to('.box', { x: 300, ease: 'elastic.out(1, 0.3)' }); // springy oscillation before settling
gsap.to('.box', { x: 300, ease: 'bounce.out' });    // simulates a physical bounce
gsap.to('.box', { x: 300, ease: 'none' });          // linear, no easing — correct choice for
                                                      // scroll-scrubbed animations tied 1:1 to
                                                      // scroll position (see 8.6), since the
                                                      // "easing" there comes from the user's
                                                      // own scroll motion, not the tween
```
**Rule of thumb for picking an ease**: `power2`/`power3` family covers 90% of real UI
animation needs (subtle, professional); `back`/`elastic`/`bounce` read as playful/attention-
grabbing and are easy to overuse — reserve them for one hero moment, not every micro-
interaction, or the UI starts to feel like a cartoon.

### Stagger — Animating Many Elements With a Cascading Delay

```js
gsap.from('.card', {
  opacity: 0,
  y: 30,
  duration: 0.5,
  stagger: 0.1, // each subsequent .card starts 0.1s after the previous one
});

// Advanced stagger — control direction, easing of the stagger itself, or start from the center
gsap.from('.grid-item', {
  opacity: 0,
  scale: 0.5,
  stagger: {
    each: 0.05,
    from: 'center',    // 'start' | 'end' | 'center' | 'edges' | 'random' | [index]
    grid: 'auto',      // understands 2D grids, staggers outward correctly
    ease: 'power2.inOut',
  },
});
```
`stagger` is what makes a list of cards, a navigation menu's links, or a grid of images feel
deliberately choreographed rather than "all popping in at once" — an extremely high-leverage,
low-effort GSAP feature to master early.

## 8.6 ScrollTrigger — Scroll-Driven Animation

`ScrollTrigger` is GSAP's official plugin for triggering, scrubbing, and pinning animations
based on scroll position — it's the modern, robust replacement for hand-rolled scroll-event
listeners (which suffer from jank, since native `scroll` events fire far more often than a
frame budget allows, unlike ScrollTrigger which is rAF-synced internally).

```js
import { gsap } from 'gsap';
import { ScrollTrigger } from 'gsap/ScrollTrigger';
gsap.registerPlugin(ScrollTrigger); // MUST register plugins before use

// Trigger a one-shot animation when an element enters the viewport
gsap.from('.fade-section', {
  opacity: 0,
  y: 50,
  duration: 0.8,
  scrollTrigger: {
    trigger: '.fade-section',
    start: 'top 80%',   // animation starts when the trigger's TOP hits 80% down the viewport
    end: 'bottom 20%',
    toggleActions: 'play none none reverse', // onEnter onLeave onEnterBack onLeaveBack
    markers: true,       // DEBUG ONLY — draws visible start/end markers, remove for production
  },
});

// Scrub — tie animation progress DIRECTLY to scroll position (no easing of its own —
// the user's scroll IS the easing, hence ease: 'none' from 8.5)
gsap.to('.parallax-image', {
  yPercent: -30,
  ease: 'none',
  scrollTrigger: {
    trigger: '.parallax-section',
    start: 'top bottom',
    end: 'bottom top',
    scrub: true,     // or a number like `scrub: 1` for a smoothing delay in seconds
  },
});

// Pin — freeze an element in place while its trigger section scrolls past (classic
// "sticky storytelling" effect used in scroll-driven landing pages)
ScrollTrigger.create({
  trigger: '.pin-section',
  start: 'top top',
  end: '+=1000',    // stay pinned for 1000px of additional scroll
  pin: true,
  pinSpacing: true, // reserves the space so content below doesn't jump when unpinned
});

// Timeline + ScrollTrigger together — scrub an entire choreographed sequence with scroll
const tl = gsap.timeline({
  scrollTrigger: { trigger: '.story-section', start: 'top top', end: '+=2000', scrub: 1, pin: true },
});
tl.to('.layer-1', { x: 100 })
  .to('.layer-2', { x: -100 }, '<')
  .to('.headline', { scale: 1.5 });
```

### `start`/`end` Syntax Decoded

`"top 80%"` means: **the trigger element's `top`** aligns with **80% down the viewport
height**. The general format is `"<trigger-position> <viewport-position>"`, where each side
can be `top`/`center`/`bottom` or a percentage/pixel value. This two-part syntax trips up
almost everyone at first — always leave `markers: true` on during development so you can see
exactly where the start/end lines land, then remove it before shipping.

### Common ScrollTrigger Gotchas ("tinkering" tips)

- **Always `gsap.registerPlugin(ScrollTrigger)`** before use, or the plugin silently no-ops.
- **Dynamic content changing layout height** (images loading late, accordions expanding) can
  desync trigger positions calculated before that content loaded — call
  `ScrollTrigger.refresh()` after content/images finish loading, or use `ScrollTrigger.config({
  ignoreMobileResize: true })`/`invalidateOnRefresh: true` for responsive robustness.
- **`scrub: true` vs `scrub: 1`**: `true` ties animation progress to scroll position with zero
  lag (can feel abrupt); a numeric value adds that many seconds of smoothing catch-up lag,
  which usually feels more premium for parallax/storytelling effects.
- Combine with `will-change: transform` (Part 3.6) on the pinned/animated element for the
  smoothest possible experience on lower-end devices, but remove it once the effect area has
  scrolled fully past to free GPU memory.

## 8.7 GSAP + React Integration

The single biggest mistake developers make combining GSAP with React is fighting React's
render cycle — GSAP directly mutates the DOM's inline styles, which is exactly what React
normally "owns." The fix is to always scope GSAP animations to a `ref` and clean them up
properly, never using `document.querySelector` (which can grab stale/wrong elements across
re-renders or in strict mode's double-invoke).

```jsx
import { useRef } from 'react';
import { useGSAP } from '@gsap/react'; // official React hook, handles cleanup for you
import { gsap } from 'gsap';

gsap.registerPlugin(useGSAP);

function Hero() {
  const container = useRef(null);

  useGSAP(() => {
    // any selector text queries here are automatically SCOPED to `container.current`
    gsap.from('.title', { opacity: 0, y: 40, duration: 0.8 });
    gsap.from('.subtitle', { opacity: 0, y: 20, duration: 0.6, delay: 0.2 });
    // all tweens/timelines created inside useGSAP are automatically reverted
    // (killed + inline styles removed) on unmount or when dependencies change — no manual
    // cleanup code needed, unlike a raw useEffect approach below.
  }, { scope: container });

  return (
    <div ref={container}>
      <h1 className="title">Welcome</h1>
      <p className="subtitle">Build something great.</p>
    </div>
  );
}
```

### The Manual `useEffect` + `gsap.context()` Pattern (if not using `@gsap/react`)

```jsx
useEffect(() => {
  const ctx = gsap.context(() => {
    gsap.from('.title', { opacity: 0, y: 40 });
    gsap.to('.box', { x: 100, scrollTrigger: { trigger: '.box', start: 'top 80%' } });
  }, containerRef); // scope

  return () => ctx.revert(); // cleanup — kills tweens AND removes any ScrollTriggers created inside
}, []);
```
`gsap.context()`/`useGSAP`'s automatic cleanup matters enormously in React specifically
because of **React 18 Strict Mode**, which intentionally mounts, unmounts, and re-mounts every
component once in development to surface exactly this class of cleanup bug — animations (and
especially ScrollTrigger instances) created without proper cleanup will silently double up or
leak on every Strict Mode remount, a very common "why does my GSAP animation look broken only
in development" support question.

### Animating on Data/Prop Changes

```jsx
function ProgressBar({ percent }) {
  const barRef = useRef(null);
  useGSAP(() => {
    gsap.to(barRef.current, { width: `${percent}%`, duration: 0.4, ease: 'power2.out' });
  }, [percent]); // re-runs the animation whenever `percent` changes, same dependency-array
                 // model as useEffect
  return <div className="track"><div ref={barRef} className="bar" /></div>;
}
```

## 8.8 Framer Motion — Animation Idiomatic to React

Framer Motion (now "Motion for React") integrates animation directly into React's declarative
model — instead of imperatively telling elements to animate (GSAP's style), you describe
**states** and Motion figures out the transition between them, which composes very naturally
with React's own render-as-a-function-of-state philosophy.

```jsx
import { motion, AnimatePresence } from 'framer-motion';

function Card({ isOpen }) {
  return (
    <motion.div
      initial={{ opacity: 0, y: 20 }}
      animate={{ opacity: 1, y: 0 }}
      exit={{ opacity: 0, y: -20 }}
      transition={{ duration: 0.3, ease: 'easeOut' }}
      whileHover={{ scale: 1.03 }}
      whileTap={{ scale: 0.97 }}
      drag="x"
      dragConstraints={{ left: 0, right: 0 }}
    >
      Content
    </motion.div>
  );
}

// AnimatePresence enables EXIT animations — normally, once React unmounts a component,
// it's just gone; AnimatePresence keeps it mounted just long enough to play `exit`,
// then removes it.
function Modal({ isOpen }) {
  return (
    <AnimatePresence>
      {isOpen && (
        <motion.div initial={{ opacity: 0 }} animate={{ opacity: 1 }} exit={{ opacity: 0 }}>
          I animate in AND out
        </motion.div>
      )}
    </AnimatePresence>
  );
}

// Variants — named animation states, propagated to children automatically for orchestration
const listVariants = {
  hidden: { opacity: 0 },
  visible: { opacity: 1, transition: { staggerChildren: 0.1 } },
};
const itemVariants = { hidden: { opacity: 0, x: -20 }, visible: { opacity: 1, x: 0 } };
function List({ items }) {
  return (
    <motion.ul variants={listVariants} initial="hidden" animate="visible">
      {items.map(item => <motion.li key={item.id} variants={itemVariants}>{item.text}</motion.li>)}
    </motion.ul>
  );
}

// layout animations — Motion automatically animates POSITION/SIZE changes caused by
// layout shifts (reordering, filtering, resizing) without you computing any FLIP math manually
<motion.div layout>{content}</motion.div>
```

### GSAP vs Framer Motion — The Interview Answer

> "GSAP is a general-purpose, framework-agnostic animation engine with the deepest feature set
> (timelines, ScrollTrigger, SVG/morphing plugins, physics) and imperative, fine-grained
> control — better for complex choreography, scroll storytelling, marketing sites, and
> canvas/SVG-heavy work. Framer Motion is built specifically for React, describes animations
> declaratively as part of component state/variants, and shines for UI micro-interactions,
> exit animations, gesture-driven UI (drag/hover/tap), and automatic layout animations — less
> setup for 'React-shaped' problems, but a narrower toolset than GSAP for large-scale scroll
> choreography." Many production apps use both: Framer Motion for component-level
> interactions, GSAP/ScrollTrigger for a scroll-driven hero or landing page section.

## 8.9 SVG Animation

```html
<svg viewBox="0 0 200 200">
  <path id="draw-path" d="M10 100 Q 100 10 190 100" stroke="black" fill="none" stroke-width="4"/>
</svg>
```
```css
/* The classic "line draw" technique using stroke-dasharray/stroke-dashoffset */
#draw-path {
  stroke-dasharray: 1000;   /* a dash length longer than the total path length */
  stroke-dashoffset: 1000;  /* pushes the entire dash off the start, hiding the line */
  animation: draw 2s ease forwards;
}
@keyframes draw {
  to { stroke-dashoffset: 0; } /* reveals the line progressively as offset shrinks to 0 */
}
```
```js
// GSAP equivalent, with a helper to get the EXACT path length instead of guessing 1000
const path = document.querySelector('#draw-path');
const length = path.getTotalLength();
gsap.set(path, { strokeDasharray: length, strokeDashoffset: length });
gsap.to(path, { strokeDashoffset: 0, duration: 2, ease: 'power2.inOut' });

// GSAP's DrawSVGPlugin (paid Club GreenSock plugin) simplifies this to one line:
// gsap.from(path, { drawSVG: '0%', duration: 2 });
```
Morphing one SVG shape into another (`MorphSVGPlugin`) and animating along a motion path
(`MotionPathPlugin`) are further GSAP premium plugins worth knowing exist for interview
breadth, even if you haven't used them directly.

## 8.10 The FLIP Technique — Smooth Layout-Change Animations

FLIP stands for **F**irst, **L**ast, **I**nvert, **P**lay — a technique for animating layout
changes (an element moving from one position/size to a very different one, e.g., a card
expanding to fill the screen) smoothly, by animating only cheap `transform`s instead of
expensive layout properties:

1. **First**: record the element's current bounding box (`getBoundingClientRect()`) *before*
   the layout change.
2. **Last**: apply the layout change instantly (e.g., add the "expanded" class), then
   immediately record the *new* bounding box.
3. **Invert**: compute the delta between First and Last, and apply an inverse `transform`
   (translate + scale) so the element *visually* still appears in its First position/size,
   even though it's now laid out in its Last position/size.
4. **Play**: animate that inverse transform back to `transform: none`, using cheap
   compositor-only properties for the entire perceived motion.

```js
// Simplified manual FLIP
const first = element.getBoundingClientRect();
element.classList.add('expanded'); // the actual layout change
const last = element.getBoundingClientRect();

const deltaX = first.left - last.left;
const deltaY = first.top - last.top;
const deltaScaleX = first.width / last.width;
const deltaScaleY = first.height / last.height;

element.style.transformOrigin = 'top left';
element.style.transform = `translate(${deltaX}px, ${deltaY}px) scale(${deltaScaleX}, ${deltaScaleY})`;
element.style.transition = 'transform 0s'; // snap to inverted position with no visible jump

requestAnimationFrame(() => {
  element.style.transition = 'transform 0.4s ease-out';
  element.style.transform = ''; // animate to the REAL final position/size
});
```
GSAP's `Flip` plugin automates this entire dance (`Flip.getState()`/`Flip.from()`), and
Framer Motion's `layout` prop (8.8) is essentially FLIP built into the framework — knowing the
underlying FLIP algorithm is exactly what lets you explain "how does Framer Motion's `layout`
prop actually achieve that smooth reflow animation?" in an interview, rather than treating it
as magic.

## 8.11 60fps Performance Discipline & "Tinkering" Debugging Tips

- **Animate `transform`/`opacity` only** wherever visually possible (Part 3.6/6.5) — this is
  the single highest-leverage rule in this entire Part.
- **Use the DevTools Performance tab** — record while an animation plays; look at the frame
  rate chart (aim for a flat line at 60fps/16.6ms per frame budget) and the "Main" track for
  purple (Layout) or green (Paint) blocks during what should be a compositor-only animation —
  their presence means you're accidentally animating a layout/paint-triggering property.
- **`will-change: transform`** promotes an element to its own GPU layer ahead of time,
  avoiding a first-frame stutter — but apply it briefly (add just before animating, remove
  after) since every promoted layer costs GPU memory; leaving it on hundreds of elements
  permanently can *hurt* performance.
- **Reduce paint area**: animating a `box-shadow`'s spread/blur repaints a large area every
  frame; prefer animating a pre-rendered shadow's `opacity`, or use a pseudo-element trick.
- **`prefers-reduced-motion`** — always respect this accessibility media query; users with
  vestibular disorders can experience real physical discomfort from motion:
```css
@media (prefers-reduced-motion: reduce) {
  *, *::before, *::after {
    animation-duration: 0.01ms !important;
    animation-iteration-count: 1 !important;
    transition-duration: 0.01ms !important;
    scroll-behavior: auto !important;
  }
}
```
```js
// GSAP equivalent check
if (window.matchMedia('(prefers-reduced-motion: reduce)').matches) {
  gsap.globalTimeline.timeScale(100); // effectively skip animations
}
```
- **Throttle expensive scroll/resize-driven JS work** (Part 4.9's `throttle`) for anything
  *not* already handled by ScrollTrigger/IntersectionObserver's internal rAF batching.
- **Test on a throttled/low-end device profile** in DevTools (CPU 4x/6x slowdown) — an
  animation that feels buttery on your dev machine can visibly stutter on the actual target
  hardware most real users have; this is the difference between "it works on my machine" and
  production-ready animation work.

# Part 9 — Build Tools & Tooling

## 9.1 Package Managers — npm, yarn, pnpm

```bash
npm install react           # adds to dependencies, updates package.json + package-lock.json
npm install -D vitest       # adds to devDependencies (build/test tools, not needed in production)
npm ci                      # clean install EXACTLY matching package-lock.json — use in CI, never `install`
```
`package-lock.json`/`yarn.lock`/`pnpm-lock.yaml` pin the **exact resolved version** of every
dependency (including transitive/nested ones) — without a lockfile, `^1.2.3` in `package.json`
could resolve to `1.2.3` today and `1.5.0` tomorrow, silently changing what actually ships;
always commit the lockfile. `pnpm` deserves a specific mention in interviews: it stores one
single copy of each package version on disk globally and **hard-links** it into every
project's `node_modules`, saving huge amounts of disk space and install time versus npm/yarn's
per-project duplication, while still giving each project a strict, non-leaky dependency tree.

### Semantic Versioning (semver)

`MAJOR.MINOR.PATCH` (e.g., `2.4.1`): **MAJOR** = breaking changes, **MINOR** = new
backward-compatible features, **PATCH** = backward-compatible bug fixes. `^2.4.1` allows minor/
patch updates (up to but not including `3.0.0`); `~2.4.1` allows only patch updates (up to but
not including `2.5.0`).

## 9.2 Bundlers — Vite vs Webpack vs esbuild/Rollup

A bundler resolves your module import graph (`import`/`require` statements) and combines
everything into a small number of optimized output files, handling: **tree-shaking**
(eliminating unused exports from the final bundle), **code splitting** (breaking output into
multiple chunks loaded on demand, e.g. per-route), **minification**, and **asset handling**
(images, CSS, fonts).

- **Webpack**: the long-standing industry-standard bundler; extremely configurable via loaders
  (transform non-JS files) and plugins, but historically slower dev-server startup/rebuilds on
  large projects because it bundles the *entire* app graph before serving anything.
- **Vite**: the modern default for new projects. In development, it serves your source files
  **directly to the browser as native ES modules** (no full bundling step at all), using the
  browser's own `import` resolution and leaning on esbuild (written in Go, extremely fast) for
  on-demand transpilation of just the files actually requested — this is why Vite's dev server
  starts near-instantly even on huge projects. For production builds, Vite switches to Rollup
  under the hood for optimized, tree-shaken bundles.
- **esbuild/SWC**: extremely fast transpilers/minifiers written in Go/Rust respectively (vs
  Babel/Terser written in JS) — used as building blocks *inside* Vite and other modern tools
  rather than as end-user-facing bundlers themselves in most setups.

### Tree-Shaking Requires ES Modules

```js
// utils.js
export function used() { return 1; }
export function unused() { return 2; } // tree-shaken away if never imported anywhere
```
Tree-shaking relies on ES Modules' **static** import/export structure (analyzable without
running the code) — this is a core reason CommonJS (`require`/`module.exports`, whose
structure can be dynamic/conditional) is much harder to tree-shake effectively, and why
modern libraries ship an ESM build specifically to enable it.

## 9.3 Babel & the Transpilation Story

```json
// .babelrc
{ "presets": ["@babel/preset-env", "@babel/preset-react", "@babel/preset-typescript"] }
```
Babel parses modern JS/JSX/TS syntax into an AST (Abstract Syntax Tree), applies
transformation plugins, and generates equivalent code targeting older JS engines specified via
a `browserslist` config — this is how `optional chaining`, JSX, and other syntax not natively
understood by older browsers still works everywhere. Many modern toolchains (Vite, Next.js)
now default to the much faster Rust/Go-based SWC or esbuild for this exact transpilation step,
using Babel only when a project needs a specific custom Babel plugin.

## 9.4 Linting & Formatting

```json
// .eslintrc — catches BUGS and enforces code-quality rules (unused vars, hooks rules, etc.)
{ "extends": ["eslint:recommended", "plugin:react-hooks/recommended"] }
```
```json
// .prettierrc — enforces STYLE only (quotes, semicolons, line width) — never logic bugs
{ "semi": true, "singleQuote": true, "printWidth": 100 }
```
ESLint and Prettier solve different problems and are almost always used together: Prettier
auto-formats so nobody argues about tabs/spaces in code review; ESLint (with
`eslint-plugin-react-hooks`, `eslint-plugin-jsx-a11y`, etc.) catches real correctness and
accessibility issues before they reach production.

## 9.5 Module Formats — CJS vs ESM

```js
// CommonJS (Node's original format, synchronous, dynamic)
const fs = require('fs');
module.exports = { foo };

// ES Modules (the web/modern standard, static, supports top-level await)
import fs from 'fs';
export { foo };
```
Node.js now supports both (via `.mjs`/`.cjs` extensions or `"type": "module"` in
`package.json`), but ESM is the forward-looking standard across the ecosystem — know that
`require` is synchronous and resolves modules at *runtime*, while `import`/`export` are
statically analyzable at *build* time (enabling tree-shaking, as above), which is the core
technical reason the ecosystem moved toward ESM despite CJS's historical dominance.

---

# Part 10 — Testing the Frontend: Unit, Component, and E2E

## 10.1 The Testing Pyramid

```
        ▲
       / \      E2E (few) — slow, expensive, but tests the REAL user journey end-to-end
      /---\
     /     \    Integration/Component (some) — render real components, mock only the network
    /-------\
   /         \  Unit (many) — fast, isolated, test pure functions/hooks/small units
  /-----------\
```
The pyramid shape is a *guideline*, not a law: spend most of your test-writing effort on fast,
cheap unit/component tests, and reserve a small number of E2E tests for your most critical
user flows (login, checkout) since they're slow and brittle by nature (real browser, real
network-ish conditions, more moving parts to flake).

## 10.2 Unit Testing with Jest / Vitest

```js
// sum.js
export function sum(a, b) { return a + b; }

// sum.test.js
import { sum } from './sum';
import { describe, test, expect, vi } from 'vitest'; // (Jest's API is nearly identical)

describe('sum', () => {
  test('adds two positive numbers', () => {
    expect(sum(2, 3)).toBe(5);
  });
  test('handles negative numbers', () => {
    expect(sum(-1, -1)).toBe(-2);
  });
});

// Mocking
const mockFn = vi.fn().mockReturnValue(42);
mockFn(1, 2);
expect(mockFn).toHaveBeenCalledWith(1, 2);
expect(mockFn).toHaveBeenCalledTimes(1);

vi.mock('./api', () => ({
  fetchUser: vi.fn().mockResolvedValue({ id: 1, name: 'Alice' }),
}));
```
Vitest is Vite-native (shares config, near-instant watch mode via the same fast transform
pipeline) and has largely displaced Jest in new Vite-based projects, while keeping an
almost-identical API, so the concepts (describe/test/expect/mocking) transfer directly either
way.

## 10.3 Component Testing with React Testing Library (Detailed)

```jsx
import { render, screen, fireEvent, waitFor } from '@testing-library/react';
import userEvent from '@testing-library/user-event';

test('shows validation error on empty submit', async () => {
  render(<LoginForm />);
  const user = userEvent.setup();

  await user.click(screen.getByRole('button', { name: /log in/i }));

  expect(await screen.findByText(/email is required/i)).toBeInTheDocument();
});
```
**RTL's query priority (favor queries a real user/assistive-tech would use)**:
`getByRole` (best — matches accessibility tree, catches missing labels/roles as a side
effect) > `getByLabelText` > `getByPlaceholderText` > `getByText` > `getByTestId` (last
resort — `data-testid` has no real user-facing meaning). This priority order is itself a
common interview question, testing whether you understand RTL's core philosophy: **tests
should resemble how users actually interact with your app**, so refactoring internal
implementation (renaming a state variable, changing from a class to a hook) shouldn't break
tests that never should have known about that implementation detail in the first place.

`userEvent` (simulates real browser event sequences — focus, keydown, keyup, click in the
right order) is preferred over the lower-level `fireEvent` (dispatches a single synthetic
event directly) for realistic interaction simulation.

## 10.4 End-to-End Testing with Cypress / Playwright

```js
// Playwright example
import { test, expect } from '@playwright/test';

test('user can log in and see dashboard', async ({ page }) => {
  await page.goto('/login');
  await page.fill('input[name="email"]', 'user@example.com');
  await page.fill('input[name="password"]', 'password123');
  await page.click('button[type="submit"]');
  await expect(page).toHaveURL('/dashboard');
  await expect(page.getByText('Welcome back')).toBeVisible();
});
```
E2E tools drive a **real browser** (Playwright supports Chromium/Firefox/WebKit; Cypress
primarily Chromium-family) against your **actual running app** (often against a real or
realistically-mocked backend), verifying entire user journeys work end-to-end exactly as a
real user would experience them — the only test layer that catches integration issues between
frontend, backend, and infrastructure that unit/component tests structurally cannot see.
Playwright's built-in auto-waiting (retries assertions until they pass or time out, instead of
requiring manual `sleep`/`wait` calls) is a specific, commonly-cited advantage over older
Selenium-based approaches which required much more manual synchronization code.

# Part 11 — Performance & Core Web Vitals

## 11.1 Core Web Vitals

Google's Core Web Vitals are the standardized, user-centric metrics for measuring real-world
page experience (and a direct search ranking factor):

| Metric | Measures | Good threshold |
|---|---|---|
| **LCP** (Largest Contentful Paint) | Time until the largest visible content element (usually a hero image or heading) renders | ≤ 2.5s |
| **INP** (Interaction to Next Paint) | Responsiveness — time from a user interaction (click/tap/key) to the next visual update; replaced FID in 2024 | ≤ 200ms |
| **CLS** (Cumulative Layout Shift) | Visual stability — how much visible content unexpectedly shifts position during load | ≤ 0.1 |

### Improving LCP
- Optimize/compress the largest image (modern formats: WebP/AVIF), serve correctly-sized
  images via `srcset` (Part 2.5), and add `fetchpriority="high"` to the hero image.
- Eliminate render-blocking resources: inline critical CSS, `defer`/`async` non-critical JS
  (Part 2.1), preconnect to critical third-party origins (`<link rel="preconnect">`).
- Use a CDN and enable HTTP caching (`Cache-Control`) so repeat visits are near-instant.
- Server-render or statically generate above-the-fold content instead of requiring a full
  client-side JS bundle to download+execute+render it (Part 1.3).

### Improving INP
- Break up long JavaScript tasks (anything blocking the main thread >50ms) into smaller
  chunks, yielding back to the browser between them (`scheduler.yield()` or chunked
  `setTimeout(fn, 0)`).
- Move genuinely heavy computation off the main thread entirely with Web Workers (Part 6.8).
- Debounce/throttle expensive handlers (Part 4.9), and avoid synchronous layout-thrashing
  work (Part 6.5) inside event handlers.

### Improving CLS
- Always reserve space for images/embeds/ads via explicit `width`/`height` or `aspect-ratio`
  (Part 2.5) before they load.
- Never inject new content **above** existing content (banners, cookie notices) — reserve the
  space up front or animate it in from below/overlay instead of pushing content down.
- Use `font-display: swap` cautiously — it prevents invisible text during font load (good for
  perceived speed) but can cause a layout shift when the real font swaps in with different
  metrics; pair with `size-adjust`/matching fallback fonts to minimize the shift.

## 11.2 Measuring Performance

- **Lighthouse** (built into Chrome DevTools, or `npx lighthouse <url>`): automated audit
  producing scores + a prioritized list of specific fixes for performance, accessibility,
  SEO, and best practices.
- **Chrome DevTools Performance tab**: records a real timeline of main-thread work, paints,
  and layout — the ground-truth tool for diagnosing *why* a specific interaction feels slow
  (see Part 8.11 for animation-specific usage).
- **`web-vitals` JS library**: measure real Core Web Vitals from actual users in production
  ("field data"), which is what search ranking and real UX actually depend on — Lighthouse's
  lab data is a useful proxy but can diverge from real-world device/network conditions.

## 11.3 Other High-Leverage Performance Techniques

- **Code splitting** (Part 7.7/9.2): only ship the JS a given route/feature actually needs.
- **Lazy loading images/components**: `loading="lazy"` (Part 2.5), `React.lazy` (Part 7.7).
- **Caching**: HTTP caching headers, service-worker-based caching for offline/repeat-visit
  speed, and in-app data caching (TanStack Query, Part 7.14).
- **Reduce JS bundle size**: audit with `source-map-explorer`/`webpack-bundle-analyzer`,
  avoid large libraries for small needs (e.g., don't import all of lodash for one function —
  `import debounce from 'lodash/debounce'` instead of `import _ from 'lodash'`).
- **Preload/prefetch**: `<link rel="preload">` for assets needed immediately on this page,
  `<link rel="prefetch">` for assets likely needed on the *next* navigation.
- **Virtualize long lists** (Part 7.7) and paginate/infinite-scroll large data sets instead of
  rendering everything at once.

---

# Part 12 — Accessibility (a11y): Building for Everyone

## 12.1 Why It Matters (Beyond Compliance)

Accessibility means your app is usable by people with visual, auditory, motor, or cognitive
disabilities — via screen readers, keyboard-only navigation, voice control, or assistive
switches. It's also legally mandated in many jurisdictions (ADA in the US, EN 301 549 in the
EU) and, pragmatically, accessible markup tends to be more robust, more SEO-friendly, and
easier to maintain in general (semantic HTML from Part 2 is 80% of the work).

## 12.2 WCAG — The Standard Framework

WCAG (Web Content Accessibility Guidelines) organizes requirements under **POUR**:
**P**erceivable (users can perceive the content — alt text, captions, sufficient color
contrast), **O**perable (users can operate the UI — full keyboard access, enough time to read/
interact, no seizure-inducing flashing), **U**nderstandable (predictable, readable, with clear
error messages), **R**obust (works correctly with a wide range of assistive technologies,
valid/semantic markup). Conformance is rated A/AA/AAA — **AA is the common legal/practical
target** most organizations aim for.

## 12.3 Keyboard Navigation

Every interactive element must be reachable via `Tab`/`Shift+Tab` and operable via
`Enter`/`Space` (and arrow keys for composite widgets like menus/tabs/comboboxes), in a
**logical order** matching the visual layout. Test your own app with the mouse unplugged —
this single exercise surfaces the majority of real accessibility bugs immediately.

```css
/* NEVER do this globally — it removes the visible focus indicator for keyboard users */
*:focus { outline: none; } /* BAD */

/* Instead, provide a clear custom focus style, or only hide it for MOUSE users specifically: */
:focus-visible {
  outline: 2px solid #3b82f6;
  outline-offset: 2px;
}
```
`:focus-visible` (vs plain `:focus`) lets the browser show focus rings only when it infers
keyboard (or other non-pointer) navigation was used, keeping the UI clean for mouse users
while never breaking it for keyboard users — a specific, frequently-tested modern a11y detail.

## 12.4 ARIA — Use Sparingly, Correctly

> "The first rule of ARIA is: don't use ARIA" if a native HTML element already provides the
> semantics/behavior you need (Part 2.8). ARIA exists to patch gaps for custom widgets native
> HTML has no equivalent for (custom dropdowns, tabs, modals, comboboxes).

```html
<div role="tablist">
  <button role="tab" aria-selected="true" aria-controls="panel-1" id="tab-1">Tab 1</button>
  <button role="tab" aria-selected="false" aria-controls="panel-2" id="tab-2">Tab 2</button>
</div>
<div role="tabpanel" id="panel-1" aria-labelledby="tab-1">Content 1</div>

<div role="dialog" aria-modal="true" aria-labelledby="dialog-title">
  <h2 id="dialog-title">Confirm Delete</h2>
  ...
</div>
```
A common, real anti-pattern is adding `role="button"` to a `<div>` and stopping there — the
correct implementation also needs `tabindex="0"` (to make it focusable), a manual `keydown`
handler for `Enter`/`Space` (native `<button>` gets both for free), and often
`aria-pressed`/`aria-disabled` state — which is exactly why "just use `<button>`" (Part 2.8)
remains the practical advice whenever possible.

## 12.5 Color Contrast & Screen Reader Basics

- Body text needs at least a **4.5:1** contrast ratio against its background (WCAG AA);
  large text (18pt+/14pt bold+) needs at least **3:1**. Check with browser DevTools' contrast
  checker or online tools — this is one of the most common real-world a11y audit failures.
- Never rely on color alone to convey information (e.g., "red = error") — pair it with an
  icon/text label for colorblind users.
- Test with an actual screen reader occasionally (VoiceOver on Mac ⌘+F5, NVDA free on
  Windows) — hearing your own app read aloud surfaces missing labels/confusing reading order
  far more effectively than reading code.

# Part 13 — Frontend System Design for Interviews

## 13.1 The General Approach

Frontend system design interviews (common at senior+ levels) aren't about producing a perfect
architecture in 45 minutes — they're about demonstrating a structured thinking process:

1. **Clarify requirements** — functional (what must it do?) and non-functional (how many
   users? real-time or eventually-consistent? mobile too? offline support needed?).
2. **Identify core components** — break the UI into a component tree, identify what state
   lives where, and what data needs to come from the server.
3. **Define the data model & API contract** — what does the backend need to send/receive?
4. **Discuss key technical challenges & tradeoffs** — this is where most of the signal comes
   from; always present 2+ options and justify your choice given the stated constraints.
5. **Address performance, accessibility, and edge cases** — empty states, error states,
   loading states, slow networks, huge data sets.

## 13.2 Design an Autocomplete / Typeahead Component

**Requirements**: as the user types, show matching suggestions from a server API, without
overwhelming the backend on every keystroke, and handle out-of-order responses correctly.

**Key challenges & answers**:
- **Debounce the input** (Part 4.9) — wait ~250-300ms after the user stops typing before
  firing a request, avoiding a request per keystroke.
- **Race conditions** — if request A (for "ap") is slow and request B (for "app") returns
  first, a naive implementation can display A's *stale* results after B's fresh ones arrive.
  Fix with an `AbortController` per request (cancel the previous request when a new one
  fires) or by tagging each request with an incrementing ID and ignoring any response whose ID
  isn't the latest.
- **Caching** — cache recent query results client-side (a simple `Map`) so re-typing a
  previously-searched prefix is instant and doesn't hit the network again.
- **Accessibility** — implement as a `combobox` ARIA pattern: `role="combobox"`,
  `aria-expanded`, `aria-activedescendant` tracking the highlighted option, full arrow-key/
  Enter/Escape keyboard support (Part 12.4).
- **UX details**: show a loading indicator during the debounce+request window, highlight the
  matched substring in each suggestion, gracefully handle zero results.

## 13.3 Design an Infinite Scroll Feed

**Requirements**: load an initial page of items, then automatically load more as the user
approaches the bottom, without janky scroll performance even after thousands of items load.

**Key challenges & answers**:
- **Detecting "near the bottom"**: use `IntersectionObserver` (Part 6.6) watching a sentinel
  element near the end of the list — far cheaper than a `scroll` event listener computing
  `scrollTop`/`scrollHeight` on every scroll pixel.
- **Pagination strategy**: cursor-based pagination (`?after=<lastItemId>`) is preferred over
  offset-based (`?page=3`) for feeds with frequently-changing data — offset pagination can
  skip or duplicate items if items are inserted/removed between page loads; a cursor anchored
  to a specific item's ID/timestamp doesn't have this problem.
- **Performance at scale**: once the DOM has thousands of rendered items, **virtualize** the
  list (Part 7.7) so only visible items (+ a buffer) are actually mounted in the DOM.
- **State to track**: current items array, cursor/next-page-token, `isLoading`,
  `hasMore`/`isEnd`, and an error state with a retry action.
- **Edge cases**: duplicate item prevention (dedupe by ID if the same item can appear across
  pages due to concurrent inserts), preserving scroll position if the user navigates away and
  back, and a "new posts available" banner pattern for feeds that update in real time above
  the user's current scroll position (rather than silently reordering content underneath them).

## 13.4 Design a Reusable Component Library / Design System

**Requirements**: a shared set of UI components (Button, Input, Modal, etc.) usable across
multiple product teams/apps, consistent in look and behavior, themeable, and accessible by
default.

**Key challenges & answers**:
- **API design philosophy**: favor **composition over configuration** — e.g., a flexible
  `<Modal><Modal.Header/><Modal.Body/><Modal.Footer/></Modal>` compound-component API scales
  better than one giant `<Modal title="" footerButtons={[...]} bodyContent={...}>` prop-soup
  component as requirements grow.
- **Styling strategy**: CSS custom properties (Part 3.9) for theming tokens (colors, spacing,
  radii) so consuming apps can override a small, well-defined surface without forking
  components; consider CSS-in-JS or CSS Modules for style encapsulation depending on the
  team's existing stack.
- **Accessibility built-in by default**: every interactive primitive (Modal, Dropdown, Tabs)
  correctly implements focus trapping, ARIA roles, and keyboard nav out of the box — so
  consuming teams get it for free rather than needing a11y expertise themselves.
- **Versioning & distribution**: publish as a versioned npm package, follow semver strictly
  (Part 9.1) since breaking changes to shared components ripple across every consuming team;
  provide codemods for breaking prop renames where possible.
- **Testing**: visual regression testing (e.g., Chromatic/Percy) on top of unit/RTL tests,
  since design systems are especially prone to *visual* regressions that functional tests
  alone won't catch.

## 13.5 Design a Client-Side Data Caching Layer

**Requirements**: avoid redundant network requests for the same data across the app, keep
displayed data reasonably fresh, and handle cache invalidation on mutations.

**Key challenges & answers**:
- **Cache key design**: key by a serialized representation of the resource + its parameters
  (e.g., `['user', userId]`, `['posts', { page: 2, filter: 'active' }]`) — this is exactly
  TanStack Query's `queryKey` model (Part 7.14).
- **Staleness strategy**: "stale-while-revalidate" — serve cached data immediately (feels
  instant), then silently refetch in the background and update the UI if the data changed,
  balancing perceived speed against freshness.
- **Invalidation on mutation**: after a POST/PUT/DELETE, either optimistically update the
  relevant cached entries directly, or mark them stale/invalidated so the next read
  re-fetches — discuss the tradeoff (optimistic updates feel faster but need a rollback path
  if the mutation actually fails on the server).
- **Memory bounds**: an unbounded cache is a memory leak risk (Part 4.9) for long-lived SPA
  sessions — discuss an LRU eviction policy or TTL-based expiry for entries not recently
  accessed.

## 13.6 Design a Real-Time Notification System (Polling vs WebSockets vs SSE)

| Approach | How it works | Best for |
|---|---|---|
| **Short polling** | Client repeatedly requests "anything new?" on an interval | Simplest to implement; wasteful if updates are infrequent; noticeable latency = poll interval |
| **Long polling** | Server holds the request open until new data exists (or a timeout), then client immediately re-requests | Lower latency than short polling without needing a persistent connection protocol; still one request per update cycle |
| **Server-Sent Events (SSE)** | Server keeps one HTTP connection open, streams events to the client as plain text | Great fit for **one-directional** server→client streams (notifications, live scores); simpler than WebSockets, auto-reconnects natively, but no client→server messages on the same channel |
| **WebSockets** | Full-duplex persistent connection, either side can send anytime | Best for **bidirectional** real-time needs (chat, collaborative editing, multiplayer); more infrastructure complexity (connection state, reconnection/backoff logic, scaling across server instances needs a pub-sub backplane like Redis) |

Discuss the actual requirement before picking: a notification bell that only needs
server→client pushes is over-engineered with WebSockets; a collaborative document editor
genuinely needs bidirectional low-latency communication.

## 13.7 Design a File Upload Component With Progress

**Requirements**: upload one or more files, show per-file progress, support cancel, handle
large files without freezing the UI, validate file type/size client-side (as UX, not
security — Part 6.4's client-validation-is-not-a-security-boundary rule still applies).

**Key challenges & answers**:
- **Progress tracking**: `XMLHttpRequest`'s `upload.onprogress` event (the Fetch API still
  lacks native upload-progress support as of this writing) or a multipart upload with
  chunking for very large files, tracking bytes-sent per chunk.
- **Concurrency control**: uploading 50 files at once can saturate the connection/exhaust
  browser connection limits — cap concurrent uploads (e.g., 3-4 at a time) and queue the rest.
- **Resumable uploads** for large files/flaky connections: chunk the file, track which chunks
  succeeded server-side, and only re-send failed/missing chunks on retry rather than
  restarting from zero.
- **UX**: per-file progress bars, a way to cancel an individual in-flight upload
  (`AbortController`, Part 6.3), clear error states per file (not one global error blocking
  everything), and drag-and-drop support (`dragover`/`drop` events + `DataTransfer.files`).

# Part 14 — Interview Question & Answer Bank

This part is written in direct Q&A format — read it after you've been through Parts 1-13 at
least once, as a rapid-fire review/self-test. For each question, try answering out loud
*before* reading the answer.

## 14.1 HTML & CSS Questions

**Q1: What's the difference between `<div>` and `<section>`?**
A: `<div>` is a purely generic, non-semantic container with no meaning to browsers/assistive
tech/search engines — use it only when no semantic element fits. `<section>` represents a
thematic grouping of content, typically with its own heading, and contributes to the page's
accessible "outline"/landmark structure (Part 2.2).

**Q2: How does the browser determine which CSS rule wins when two rules target the same
element?**
A: First by origin/importance (author `!important` > author normal > user-agent default,
roughly), then by **specificity** (ID > class/attribute/pseudo-class > element), then by
**source order** if specificity ties (later rule wins). See the full specificity table in
Part 3.2.

**Q3: Explain the CSS box model, including `box-sizing`.**
A: Every element is content + padding + border + margin, nested outside-in. By default
(`content-box`), `width`/`height` apply only to the content box; `box-sizing: border-box`
makes them apply to content+padding+border combined, which is what almost every real project
uses globally (Part 3.1).

**Q4: What is margin collapsing, and when does it NOT happen?**
A: Vertically adjacent margins between block siblings in normal flow collapse to the larger of
the two, not their sum. It does NOT happen for horizontal margins, for flex/grid children, or
for elements with `overflow` other than `visible` (Part 3.1).

**Q5: `position: absolute` — relative to what?**
A: The nearest ancestor with a `position` other than `static` (i.e., `relative`, `absolute`,
`fixed`, or `sticky`); if none exists, relative to the initial containing block (viewport)
(Part 3.3).

**Q6: Flexbox vs Grid — when do you reach for each?**
A: Grid for genuinely 2D layouts (page skeletons, dashboards, galleries); Flexbox for 1D
alignment along a single axis (navbars, button groups, centering). They compose — Grid for
the page, Flexbox inside individual grid cells (Part 3.5).

**Q7: Why should you animate `transform`/`opacity` instead of `width`/`top`/`left`?**
A: `transform`/`opacity` changes can be handled entirely by the GPU compositor thread, without
triggering layout or paint; `width`/`top`/`left` force a synchronous layout recalculation on
every frame, which is far more expensive and causes jank (Part 3.6, Part 6.5).

**Q8: What does `alt=""` (empty) vs omitting `alt` entirely mean for an `<img>`?**
A: `alt=""` explicitly marks the image as decorative — screen readers skip it entirely.
Omitting `alt` is invalid/ambiguous and some screen readers fall back to announcing the file
name, which is a worse experience than an explicit empty alt for decorative images (Part 2.5).

**Q9: How would you center a div both horizontally and vertically?**
A: The modern one-liner: `display: flex; justify-content: center; align-items: center;` on
the parent. Grid equivalent: `display: grid; place-items: center;`. Older techniques
(absolute positioning + negative margin/transform, or `margin: auto` with defined
width/height) still work but are more verbose (Part 3.4).

**Q10: What's the difference between `visibility: hidden`, `display: none`, and
`opacity: 0`?**
A: `display: none` removes the element from the layout entirely (no space reserved,
unreachable by keyboard/screen readers). `visibility: hidden` keeps its layout space but hides
it visually and from most assistive tech (though it's still technically in the DOM/render
tree). `opacity: 0` keeps the element fully visible-to-layout, fully interactive (still
clickable/focusable!) and present to assistive tech — just invisible pixel-wise, which is a
common source of "why can I still click/tab into that invisible thing?" bugs.

**Q11: What is `@layer` and why would you use it?**
A: CSS Cascade Layers let you control which group of rules wins **by declared layer order**,
independent of selector specificity — useful for architecting large codebases (e.g., a
`utilities` layer that should always beat a `components` layer regardless of each rule's own
specificity) (Part 3.2).

**Q12: How does `srcset`/`sizes` improve performance, and what problem does `<picture>` solve
that `srcset` alone doesn't?**
A: `srcset`/`sizes` let the browser pick the best-fitting resolution for the viewport/pixel
density, saving bandwidth. `<picture>` additionally allows serving entirely different **image
formats** (AVIF/WebP with a JPEG fallback) or **art direction** (different crops for different
breakpoints), which plain `srcset` on an `<img>` cannot do (Part 2.5).

**Q13: What's the difference between `em`, `rem`, `%`, `vw/vh`, and `px` units?**
A: `px` is an absolute unit. `em` is relative to the **current element's** font-size (compounds
awkwardly when nested). `rem` is relative to the **root** (`<html>`) font-size — predictable,
the modern default for consistent typography/spacing. `%` is relative to the parent's
corresponding dimension. `vw`/`vh` are relative to 1% of the viewport width/height —
useful for full-bleed/fluid sizing but can misbehave on mobile due to dynamic browser chrome
(address bar show/hide) affecting `vh`; `dvh`/`svh`/`lvh` (dynamic/small/large viewport height)
are the modern fix for that specific mobile quirk.

**Q14: Explain `z-index` and stacking contexts.**
A: `z-index` only has effect on positioned elements (`position` other than `static`) and only
compares within the same **stacking context** — a new stacking context is created by several
triggers (e.g., `position: fixed`/`sticky`, `opacity < 1`, `transform`, `filter`, `will-change`
naming certain properties). A `z-index: 9999` element can still render *behind* a
`z-index: 1` element if they belong to different stacking contexts (e.g., one is nested inside
a parent with `opacity: 0.99`, which created its own stacking context) — a genuinely tricky,
frequently-misunderstood CSS mechanic worth being able to explain with an example.

**Q15: What is BEM, and what problem does it solve?**
A: A naming convention (`.block__element--modifier`) that keeps every class flat (single-class
specificity, no nesting-based specificity wars) and self-documenting about a class's role and
relationship to its parent block (Part 3.11).

## 14.2 JavaScript Questions

**Q1: What's the difference between `==` and `===`?**
A: `===` never coerces types (different types are always unequal); `==` coerces one/both
operands per a specific, often-surprising set of rules before comparing (Part 4.1). Always
default to `===`.

**Q2: Explain `var` vs `let` vs `const`.**
A: `var` is function-scoped, hoisted and initialized to `undefined` immediately. `let`/`const`
are block-scoped, hoisted but left in the "Temporal Dead Zone" until their declaration line
executes. `const` prevents reassignment of the binding, not mutation of the value it points to
(Part 4.2).

**Q3: What is a closure? Give a practical use case.**
A: A function bundled with references to its surrounding lexical scope, "remembering" those
variables even after the outer function has returned. Practical uses: private state/module
pattern, memoization, debounce/throttle, currying (Part 4.3).

**Q4: What does this code log, and why?**
```js
for (var i = 0; i < 3; i++) { setTimeout(() => console.log(i), 0); }
```
A: `3, 3, 3` — all three closures share the same function-scoped `var i`, which is `3` by the
time any callback actually runs (after the synchronous loop has fully finished). Using `let`
instead prints `0, 1, 2`, because `let` creates a fresh binding per iteration (Part 4.2).

**Q5: Explain the four rules for determining `this`.**
A: In priority order: `new` binding (new object), explicit binding (`call`/`apply`/`bind`),
implicit binding (whatever is left of the dot at call time), default binding
(`undefined`/global). Arrow functions ignore all of these — they capture `this` lexically from
where they were *defined*, permanently (Part 4.4).

**Q6: How does prototypal inheritance work, and how does `class` syntax relate to it?**
A: Every object has an internal `[[Prototype]]` link to another object it delegates property
lookups to when a property isn't found on itself. `class`/`extends` is syntactic sugar over
this exact mechanism — `Dog.prototype.__proto__ === Animal.prototype` under the hood
(Part 4.5).

**Q7: Explain the event loop: call stack, microtask queue, macrotask queue.**
A: Synchronous code runs on the call stack. Once it's empty, the engine drains the **entire**
microtask queue (promise callbacks, `queueMicrotask`) before processing even one macrotask
(`setTimeout`, DOM events). This is why `Promise.resolve().then(...)` always logs before a
`setTimeout(..., 0)` scheduled earlier in the same synchronous block (Part 4.7).

**Q8: What's the difference between `Promise.all`, `Promise.allSettled`, `Promise.race`, and
`Promise.any`?**
A: `all` resolves when every promise resolves, rejects immediately on the first rejection.
`allSettled` always resolves, giving per-promise status, never short-circuits. `race` settles
as soon as the first promise settles (success OR failure). `any` resolves on the first
*fulfillment*, only rejecting if all reject (Part 4.7).

**Q9: Why does this function not work as intended, and how do you fix it?**
```js
async function processAll(ids) {
  ids.forEach(async (id) => { await processItem(id); });
  console.log('done');
}
```
A: `forEach` doesn't wait for its (async) callback's promise — all three `processItem` calls
fire, but the function returns and logs `'done'` immediately, before any of them resolve.
Fix with a `for...of` loop + `await` for sequential processing, or `Promise.all(ids.map(...))`
for parallel processing (Part 4.7).

**Q10: What are the 8 falsy values in JavaScript?**
A: `false, 0, -0, 0n, "", null, undefined, NaN`. Notably `[]` and `{}` are truthy (Part 4.1).

**Q11: Explain `debounce` vs `throttle`.**
A: Debounce delays execution until a pause of silence (fires once, after the user *stops*
triggering the event for N ms — e.g., search-as-you-type). Throttle guarantees execution at
most once per interval, regardless of how often the event fires (e.g., scroll handlers)
(Part 4.9).

**Q12: What causes memory leaks in JavaScript, given it has automatic garbage collection?**
A: Anything *external* keeping a reference alive longer than intended: un-removed event
listeners, uncleared `setInterval` timers, detached DOM nodes still referenced by a variable,
unbounded caches, and closures over large objects captured by long-lived callbacks (Part 4.9).

**Q13: What's the difference between `null` and `undefined`?**
A: `undefined` means a variable has been declared but not assigned a value (or a function
parameter wasn't passed, or a property doesn't exist on an object). `null` is an explicit,
intentional "no value" assignment made by the programmer. `typeof undefined === 'undefined'`,
`typeof null === 'object'` (a longstanding language quirk). `null == undefined` is `true`
(special-cased), but `null === undefined` is `false`.

**Q14: What does `Object.freeze()` do, and what are its limits?**
A: Prevents adding/removing/reassigning an object's own top-level properties (silently fails
in non-strict mode, throws in strict mode). It is **shallow** — nested objects inside a frozen
object are NOT frozen and remain fully mutable, a common gotcha.

**Q15: Explain currying with an example.**
A: Transforming a function that takes multiple arguments into a sequence of functions each
taking a single argument: `const add = a => b => c => a + b + c; add(1)(2)(3) // 6`. Useful for
partial application — pre-filling some arguments to create a specialized, reusable function
(Part 4.3).

**Q16: What is the difference between `Array.prototype.map` and `forEach`?**
A: `map` returns a **new array** built from the callback's return values, intended for
transformation. `forEach` always returns `undefined` and is intended purely for side effects.
Using `map` when you don't use its return value (i.e., only for side effects) is a common code
smell flagged in reviews.

**Q17: What is a generator function, and what's one real use case?**
A: A function (`function*`) that can pause and resume execution via `yield`, producing a
sequence of values lazily on demand rather than computing them all upfront. Real uses:
custom iterables, infinite sequences generated lazily, and as the foundation of libraries like
Redux-Saga for managing complex async flows (Part 4.8).

**Q18: What does `structuredClone()` do, and how does it differ from
`JSON.parse(JSON.stringify(x))` for deep cloning?**
A: `structuredClone()` is a native browser API for deep-cloning most JS values (including
`Date`, `Map`, `Set`, circular references, typed arrays) without the older
`JSON.parse(JSON.stringify(x))` trick's limitations — that trick silently drops `undefined`
values/functions, converts `Date` objects to strings, can't handle circular references
(throws), and loses `Map`/`Set` entirely.

**Q19: What's the difference between shallow copy and deep copy? Give an example where a
shallow copy causes a bug.**
A: A shallow copy (`{...obj}`, `[...arr]`, `Object.assign({}, obj)`) copies only the top-level
properties — nested objects/arrays are still shared **references** with the original. Bug
example: `const copy = {...original}; copy.nested.value = 5;` also mutates
`original.nested.value`, because `copy.nested` and `original.nested` point to the exact same
object.

**Q20: What is "hoisting"? Does it apply the same way to function declarations and function
expressions?**
A: Hoisting is the JS engine's behavior of processing declarations before executing code
line-by-line. Function *declarations* (`function foo(){}`) are hoisted completely — both the
name and the function body — so you can call them before their line in the source. Function
*expressions* (`const foo = function(){}` or `const foo = () => {}`) only hoist the variable
declaration (as `undefined` for `var`, or into the TDZ for `let`/`const`) — calling them
before their assignment line throws (Part 4.2, 4.6).

## 14.3 TypeScript Questions

**Q1: What's the difference between `any` and `unknown`?**
A: `any` disables type checking entirely — you can do anything with it, no compiler
complaints, and it "infects" anything it touches. `unknown` is type-safe: you can assign
anything to it, but must narrow its type (via `typeof`/`instanceof`/type guards) before using
it (Part 5.1).

**Q2: `interface` vs `type` — when would you choose one over the other?**
A: `interface` supports declaration merging (re-opening to add more members) and reads more
naturally for object/class shapes, especially library-facing APIs. `type` can alias unions,
tuples, primitives, and mapped/conditional types — things `interface` cannot express. Common
guidance: `interface` for public object shapes, `type` for unions and utility compositions
(Part 5.2).

**Q3: Explain generics with a simple example.**
A: Generics let you write a function/type that works with multiple types while preserving the
relationship between input and output types: `function identity<T>(x: T): T { return x; }` —
calling `identity(42)` returns `number`, calling `identity('hi')` returns `string`, fully
type-checked, without needing an `any` escape hatch or duplicate functions per type (Part 5.3).

**Q4: What does `Partial<T>` do? Give a real use case.**
A: Makes every property of `T` optional. Common use: an `updateUser(id, changes:
Partial<User>)` function where a caller only needs to supply the fields they're actually
changing, not the entire object (Part 5.4).

**Q5: What is a type guard, and why are they needed?**
A: A function or expression that narrows a broader type (like a union) to a more specific one
within a conditional block, e.g. `function isCat(a: Cat | Dog): a is Cat { return 'meow' in a;
}`. Needed because TypeScript can't always infer which branch of a union you're in just from
runtime logic alone — a type guard explicitly tells the compiler (Part 5.7).

**Q6: What does `strictNullChecks` actually change?**
A: Without it, `null`/`undefined` are silently assignable to every type, defeating much of the
type system's safety. With it enabled (part of `"strict": true`), `string` and `string | null`
become meaningfully different types, and you're forced to explicitly handle the null/undefined
case wherever it's possible — catching a huge class of "cannot read property of undefined"
runtime errors at compile time instead (Part 5.9).

## 14.4 React Questions

**Q1: What is the virtual DOM, and why does React use it?**
A: A lightweight in-memory JS representation of the desired UI tree. React diffs the new tree
against the previous one (reconciliation) and applies only the minimal necessary real DOM
mutations, which is both faster than naive full-tree DOM rewrites and lets you write UI
declaratively ("here's what it should look like") instead of imperatively managing DOM
mutations by hand (Part 7.1).

**Q2: Why does a component re-render? What's the default relationship between parent and
child re-renders?**
A: A component re-renders when its own state changes, when its parent re-renders (by
**default, every child re-renders when its parent does**, regardless of whether its own props
changed), or when a consumed context value changes. This default cascading re-render is why
`React.memo`, `useMemo`, and `useCallback` exist (Part 7.7).

**Q3: What does `React.memo` actually do, and when does it fail to help?**
A: It skips a component's re-render if a **shallow comparison** of its props is unchanged from
the last render. It fails to help when a prop is a new object/array/function reference every
render (even with identical contents) — which is exactly why `useMemo`/`useCallback` are often
paired with `React.memo` on the parent side (Part 7.7).

**Q4: Why is using array index as a `key` often a bug, specifically?**
A: When a list can be reordered, filtered, or have items inserted/removed from the middle, the
index no longer reliably identifies "the same logical item" across renders — React can
mis-associate internal state (e.g., an input's typed value, or a CSS transition) with the
wrong row, since it matches by key, not by content (Part 7.7).

**Q5: Explain the `useEffect` dependency array's three main forms.**
A: Omitted → runs after every render. `[]` → runs once, after initial mount only.
`[dep1, dep2]` → runs after mount and again whenever any listed dependency changes (compared
via `Object.is`) (Part 7.4).

**Q6: Why does this counter only increment by 1 total, not 2, when both lines run in the same
handler?**
```jsx
function handleClick() {
  setCount(count + 1);
  setCount(count + 1);
}
```
A: Both calls close over the *same* `count` value from the current render (state updates are
async/batched) — use the functional form `setCount(prev => prev + 1)` twice to correctly get
+2, since it always operates on the latest pending state (Part 7.3).

**Q7: What are the Rules of Hooks, and why do they exist?**
A: (1) Only call hooks at the top level, never in loops/conditions/nested functions. (2) Only
call hooks from React function components or other custom hooks. They exist because React
associates each hook call with a persistent state slot based purely on **call order** across
renders — changing that order between renders corrupts React's internal bookkeeping
(Part 7.6).

**Q8: What is prop drilling, and how does Context solve (and not fully solve) it?**
A: Prop drilling is passing a prop down through many intermediate components that don't
themselves use it, purely to get it to a deeply nested descendant. `useContext` lets a
descendant read a value directly from a `Provider` higher up, skipping the intermediates — but
Context re-renders **every consumer** whenever the context value changes, with no built-in
granular subscription, so it's not a full substitute for a real state-management library for
frequently-changing, large-scale state (Part 7.8).

**Q9: Controlled vs uncontrolled inputs — what's the tradeoff?**
A: Controlled inputs have their `value` driven by React state, re-rendering on every keystroke
— gives full control (validation, formatting) at the cost of a render per keystroke.
Uncontrolled inputs let the DOM manage their own value, read via a `ref` only when needed —
better performance for very large forms, less built-in control (Part 7.9).

**Q10: Why must error boundaries be class components?**
A: `getDerivedStateFromError` and `componentDidCatch` are class lifecycle methods with no
function-component/hook equivalent in React's stable public API — there is currently no
`useErrorBoundary` hook (Part 7.10).

**Q11: What do error boundaries NOT catch?**
A: Errors inside event handlers, errors in asynchronous code (e.g., inside a `setTimeout` or
a `.then()`), and errors during server-side rendering — only errors thrown during rendering,
in lifecycle methods, or in constructors of the tree below the boundary (Part 7.10).

**Q12: What is the difference between Server Components and Client Components in
Next.js/React?**
A: Server Components render only on the server, ship zero JS for their own code to the
client, and can directly `await` data — but cannot use state, effects, or browser APIs. Client
Components (`'use client'`) are the classic hooks-based components — interactive, stateful,
hydrated in the browser (Part 7.12).

**Q13: What causes a hydration mismatch, and name two common real causes.**
A: The server-rendered HTML doesn't exactly match what the client would produce on its first
render pass. Common causes: using `Date.now()`/`Math.random()` directly during render (differs
between server render time and client render time), and inconsistent `typeof window !==
'undefined'` branching that renders different output server-side vs client-side (Part 7.12).

**Q14: When would you reach for Context vs Zustand/Redux vs TanStack Query?**
A: Context for simple, infrequently-changing global values (theme, locale, current user
identity). Zustand/Redux for real, frequently-updating shared **client** state needing
granular, non-cascading subscriptions. TanStack Query/SWR specifically for **server state**
(fetched data) — caching, staleness, loading/error states — which is a fundamentally different
problem from client state and shouldn't be manually reimplemented with `useState`/Redux
(Part 7.14).

**Q15: What is list virtualization, and when do you need it?**
A: Rendering only the currently-visible subset of a long list (plus a small buffer) instead of
every item, recycling DOM nodes as the user scrolls. Needed once a list has enough items
(typically thousands+) that even fully memoized rendering of every row becomes a real DOM-size
performance problem (Part 7.7, Part 13.3).

## 14.5 Animation & GSAP Questions

**Q1: Why do performant animations only touch `transform` and `opacity`?**
A: Those two properties can be updated purely on the GPU compositor thread — no layout
recalculation, no repaint — so the browser can hit a steady 60fps even under main-thread load.
Animating `width`/`top`/`left`/`margin` forces a synchronous layout recalculation every frame,
which is dramatically more expensive and the #1 cause of janky animation (Part 3.6, 8.11).

**Q2: `gsap.from()` vs `gsap.fromTo()` — why is `fromTo` often safer?**
A: `.from()` infers the "to" state from the element's *current* computed styles at the moment
the tween runs — if prior state (a previous animation, an added CSS class, a race condition)
already changed those styles, the animation's true starting point becomes inconsistent.
`.fromTo()` makes both endpoints fully explicit, so the result is reproducible regardless of
what happened before (Part 8.3).

**Q3: What does the GSAP timeline position parameter `"-=0.3"` mean?**
A: Start this tween 0.3 seconds **before** the previous tween in the timeline finishes,
creating an overlap. `"+=0.3"` creates a 0.3s gap instead, and `"<"` starts at the same moment
the previous tween *started* (Part 8.4).

**Q4: Why should `ease: 'none'` be used for scroll-scrubbed ScrollTrigger animations?**
A: When `scrub` ties animation progress directly to scroll position, the user's own scroll
motion supplies the "easing" — applying an additional easing curve on top would fight against
the 1:1 scroll-to-progress mapping and feel disconnected/laggy relative to the user's actual
scroll input (Part 8.5, 8.6).

**Q5: How do you properly clean up GSAP animations inside a React component?**
A: Use the official `useGSAP` hook (`@gsap/react`) with a `scope` ref, or manually wrap
animations in `gsap.context()` inside a `useEffect` and call `ctx.revert()` in the cleanup
function. This matters especially under React 18 Strict Mode, which intentionally double-
mounts components in development to surface exactly this class of missing-cleanup bug
(Part 8.7).

**Q6: Explain the FLIP technique in your own words.**
A: First (record the element's starting bounding box), Last (apply the real layout change,
then record the new bounding box), Invert (apply a transform that visually cancels the
difference, so it still *looks* like it's in the First position/size even though it's
technically laid out in the Last position/size), Play (animate that inverse transform back to
none). The entire technique exists to turn an expensive layout-change animation into a cheap
compositor-only transform animation (Part 8.10).

**Q7: What is `stagger`, and why is it valuable for lists/grids of elements?**
A: A cascading delay applied automatically across multiple targets of the same tween, so
elements animate in sequence rather than all simultaneously — makes a list of cards or grid of
images feel deliberately choreographed instead of "popping in all at once" for very little
added code (Part 8.5).

**Q8: What does `will-change: transform` do, and what's the risk of overusing it?**
A: It hints to the browser to promote that element to its own GPU compositor layer ahead of
time, avoiding a stutter on the very first animation frame. The risk: every promoted layer
consumes GPU memory, so applying it to hundreds of elements permanently (rather than briefly,
just before/during the animation) can actually hurt performance instead of helping (Part 3.6,
8.11).

**Q9: How do you respect `prefers-reduced-motion` for users with vestibular disorders?**
A: In CSS, use an `@media (prefers-reduced-motion: reduce)` block to drastically shorten/
disable animation and transition durations globally. In JS/GSAP, check
`window.matchMedia('(prefers-reduced-motion: reduce)').matches` and either skip animations or
speed up the global timeline (Part 8.11).

**Q10: GSAP vs Framer Motion — how would you decide which to use on a real project?**
A: GSAP for framework-agnostic, deeply choreographed sequences, scroll storytelling
(ScrollTrigger), and SVG/canvas-heavy work needing fine imperative control. Framer Motion for
idiomatic React component-level interactions — declarative variants, automatic exit
animations via `AnimatePresence`, gesture handling, and automatic layout animations — with
less setup for typical "React-shaped" UI problems. Many real apps use both, split by use case
(Part 8.8).

**Q11: How would you debug a specific animation that looks janky, using DevTools?**
A: Record the animation in the Performance tab; look at the frame-rate chart for dips below
60fps, and examine the "Main" thread track for purple (Layout) or unexpected green (Paint)
blocks during what should be a compositor-only transform/opacity animation — their presence
reveals you're accidentally animating a layout- or paint-triggering property somewhere
(Part 8.11).

## 14.6 Browser & Performance Questions

**Q1: Walk through what happens between typing a URL and seeing the page.**
A: DNS resolution → TCP/TLS handshake → HTTP request/response → HTML parsing into the DOM →
CSS parsing into the CSSOM → combine into a render tree → layout (compute geometry) → paint
(fill pixels) → composite (GPU assembles final frame). Scripts encountered during HTML
parsing pause parsing by default unless marked `async`/`defer` (Part 1.2, 6.5).

**Q2: What are the three Core Web Vitals, and what does each measure?**
A: LCP (loading speed — time to render the largest visible element), INP (responsiveness —
time from interaction to next visual update), CLS (visual stability — how much content
unexpectedly shifts during load) (Part 11.1).

**Q3: What causes "layout thrashing," and how do you avoid it?**
A: Interleaving DOM reads (`offsetWidth`, `getBoundingClientRect()`) and writes (`style.width
= ...`) in a loop forces the browser to synchronously recalculate layout on every iteration
instead of batching. Fix by reading all needed values first, then writing all changes after,
in two separate passes (Part 6.5).

**Q4: Why does `fetch()` not reject on a 404 or 500 response?**
A: `fetch()`'s promise only rejects on network-level failures (DNS failure, connection
refused, CORS block) — any HTTP response, including error status codes, is still a
"successful" fetch from the API's perspective. Always explicitly check `res.ok` (or
`res.status`) after `await fetch(...)` (Part 6.3).

**Q5: Why shouldn't you store an auth token in `localStorage`?**
A: `localStorage` is readable by any JavaScript running on the page, making it directly
vulnerable to theft via XSS. `httpOnly` cookies (inaccessible to JS entirely) are the safer
default for storing session/auth tokens (Part 6.4).

**Q6: What's the difference between `IntersectionObserver` and listening to the `scroll`
event to detect visibility?**
A: `IntersectionObserver` runs asynchronously, off the main scroll-handling path, and only
fires when the intersection ratio actually crosses a threshold — far cheaper than a native
`scroll` listener that fires on every scroll pixel and typically needs manual
`getBoundingClientRect()` calls (which themselves can trigger layout) on every callback
(Part 6.6).

**Q7: What is code splitting, and how does `React.lazy` implement it?**
A: Breaking your JS bundle into multiple chunks loaded on demand instead of all upfront.
`React.lazy(() => import('./Component'))` uses a dynamic `import()`, which bundlers
automatically split into a separate chunk, downloaded only when that component is actually
rendered — reducing initial bundle size for infrequently-visited routes/features (Part 7.7).

**Q8: Explain tree-shaking, and why it depends on ES Modules specifically.**
A: Tree-shaking removes exported code that's never actually imported anywhere from the final
bundle. It relies on ES Modules' **static**, analyzable import/export structure (determinable
without executing the code) — CommonJS's `require`/`module.exports` can be dynamic/
conditional, making it much harder for a bundler to safely prove a given export is truly
unused (Part 9.2).

**Q9: What is the difference between `<script>`, `<script defer>`, and `<script async>`?**
A: Plain `<script>` blocks HTML parsing while it downloads and executes, in document order.
`defer` downloads in the background without blocking parsing, then executes after parsing
completes, in document order relative to other deferred scripts. `async` downloads in the
background too, but executes **immediately upon download**, potentially out of order with
other scripts — good for independent scripts like analytics (Part 2.1).

**Q10: What's the difference between a Web Worker and the main thread?**
A: A Web Worker runs on a genuinely separate OS thread with no shared memory (communication
via message-passing) and no DOM access, existing specifically to move CPU-heavy work off the
main thread so it never blocks rendering/interaction (Part 6.8).

**Q11: What's the difference between `localStorage`, `sessionStorage`, and cookies?**
A: `localStorage` persists until explicitly cleared, shared across tabs for the same origin.
`sessionStorage` clears when the tab closes, scoped per-tab. Cookies have configurable
expiry, a small (~4KB) size limit, and are automatically sent with every matching HTTP
request — the only one the *server* can natively set/read (Part 6.4).

**Q12: How would you improve a page's LCP score?**
A: Optimize/correctly-size the largest content element's image, eliminate render-blocking
CSS/JS above the fold, use a CDN with proper caching headers, and prefer server-rendering/
static generation for above-the-fold content over requiring a full client JS bundle to render
it (Part 11.1).

## 14.7 Frontend System Design Recap Questions

**Q1: How would you prevent race conditions in an autocomplete component when responses can
arrive out of order?**
A: Use an `AbortController` to cancel the previous in-flight request when a new one fires, or
tag each request with an incrementing sequence ID and ignore any response that isn't the
latest ID (Part 13.2).

**Q2: Why is cursor-based pagination generally preferred over offset-based pagination for an
infinite-scroll feed?**
A: Offset-based pagination (`?page=3`) can skip or duplicate items if the underlying data
changes (items inserted/removed) between page loads. Cursor-based pagination
(`?after=<lastItemId>`) anchors to a specific item, avoiding that class of bug (Part 13.3).

**Q3: What's the core API design principle for a reusable component library, and why?**
A: Favor composition over configuration — flexible compound-component APIs
(`<Modal><Modal.Header/></Modal>`) scale better as requirements grow than one giant component
accepting dozens of configuration props, which becomes unwieldy and hard to extend
(Part 13.4).

**Q4: When would you choose WebSockets over Server-Sent Events for a real-time feature?**
A: When the client also needs to send messages back over the same persistent channel (chat,
collaborative editing, multiplayer). SSE is simpler and sufficient for pure one-directional
server→client streams like notifications (Part 13.6).

**Q5: What's "stale-while-revalidate," and why is it a good default caching strategy for a
client-side data layer?**
A: Serve cached data immediately (feels instant to the user), then silently refetch in the
background and update the UI if the data actually changed — balancing perceived speed against
data freshness, without a manual loading spinner on every navigation back to already-seen data
(Part 13.5).

## 14.8 Coding Challenges — Implement From Scratch

These are the classic "write this on a whiteboard/shared editor" frontend coding questions.
For each: problem statement, approach, full working code, complexity, and test cases.

### Challenge 1: Implement `debounce`

**Problem**: Write a `debounce(fn, delay)` that returns a new function which only invokes
`fn` after `delay` ms have passed since the *last* time the returned function was called.

**Approach**: Keep a single `timeoutId` in closure. Every call clears any pending timeout and
schedules a new one.

```js
function debounce(fn, delay) {
  let timeoutId;
  return function (...args) {
    clearTimeout(timeoutId);
    timeoutId = setTimeout(() => fn.apply(this, args), delay);
  };
}

// Test
const log = debounce((msg) => console.log(msg), 300);
log('a'); log('b'); log('c'); // only 'c' logs, ~300ms after the last call
```
**Complexity**: O(1) per call. **Follow-up**: add an `immediate`/`leading` option to fire on
the *first* call of a burst instead of the last (common real interview follow-up):
```js
function debounce(fn, delay, immediate = false) {
  let timeoutId;
  return function (...args) {
    const callNow = immediate && !timeoutId;
    clearTimeout(timeoutId);
    timeoutId = setTimeout(() => {
      timeoutId = null;
      if (!immediate) fn.apply(this, args);
    }, delay);
    if (callNow) fn.apply(this, args);
  };
}
```

### Challenge 2: Implement `throttle`

**Problem**: Write a `throttle(fn, limit)` that ensures `fn` runs at most once every `limit`
ms, regardless of how often the returned function is called.

```js
function throttle(fn, limit) {
  let inThrottle = false;
  let lastArgs = null;
  return function (...args) {
    if (!inThrottle) {
      fn.apply(this, args);
      inThrottle = true;
      setTimeout(() => {
        inThrottle = false;
        if (lastArgs) { fn.apply(this, lastArgs); lastArgs = null; }
      }, limit);
    } else {
      lastArgs = args; // trailing call — ensures the LAST event during the throttle
                        // window still eventually fires (common follow-up requirement)
    }
  };
}
```
**Complexity**: O(1) per call. This "trailing call" variant is a frequent follow-up — a naive
throttle without it can drop the final, most up-to-date event of a burst entirely (e.g., the
final scroll position).

### Challenge 3: Deep Clone an Object (handling circular references)

**Problem**: Implement `deepClone(obj)` without using `structuredClone` or
`JSON.parse(JSON.stringify())`, correctly handling nested objects/arrays and circular
references.

```js
function deepClone(obj, seen = new WeakMap()) {
  if (obj === null || typeof obj !== 'object') return obj; // primitives, return as-is
  if (seen.has(obj)) return seen.get(obj);                  // circular reference guard

  const clone = Array.isArray(obj) ? [] : {};
  seen.set(obj, clone);

  for (const key of Object.keys(obj)) {
    clone[key] = deepClone(obj[key], seen);
  }
  return clone;
}

// Test
const a = { name: 'A' };
a.self = a; // circular reference
const cloned = deepClone(a);
console.log(cloned.self === cloned); // true — circularity preserved, no infinite loop/stack overflow
```
**Complexity**: O(n) where n = total number of properties across the whole object graph. The
`WeakMap` (`seen`) is what prevents both infinite recursion on circular structures and
duplicate cloning of objects referenced from multiple places in the graph.

### Challenge 4: Implement a Custom `EventEmitter`

**Problem**: Build a class with `on(event, callback)`, `off(event, callback)`,
`emit(event, ...args)`, and `once(event, callback)`.

```js
class EventEmitter {
  #listeners = new Map();

  on(event, callback) {
    if (!this.#listeners.has(event)) this.#listeners.set(event, []);
    this.#listeners.get(event).push(callback);
    return this; // enables chaining: emitter.on('a', fn).on('b', fn2)
  }

  off(event, callback) {
    if (!this.#listeners.has(event)) return this;
    this.#listeners.set(event, this.#listeners.get(event).filter(cb => cb !== callback));
    return this;
  }

  emit(event, ...args) {
    (this.#listeners.get(event) || []).slice().forEach(cb => cb(...args));
    // .slice() copies the array so a listener that calls `.off()` on itself mid-emit
    // doesn't skip/corrupt the iteration of the ORIGINAL array
    return this;
  }

  once(event, callback) {
    const wrapper = (...args) => {
      this.off(event, wrapper);
      callback(...args);
    };
    return this.on(event, wrapper);
  }
}

// Test
const emitter = new EventEmitter();
const greet = (name) => console.log(`Hello, ${name}`);
emitter.on('greet', greet);
emitter.emit('greet', 'Alice'); // "Hello, Alice"
emitter.off('greet', greet);
emitter.emit('greet', 'Bob'); // (nothing logs)
```
**Complexity**: O(1) for `on`/`off` lookups (amortized, given `Map`), O(k) for `emit` where k =
number of listeners for that event.

### Challenge 5: Polyfill `Promise.all`

**Problem**: Implement `Promise.all` from scratch — resolves with an array of all results in
original order once every promise resolves, rejects immediately if any promise rejects.

```js
function promiseAll(promises) {
  return new Promise((resolve, reject) => {
    const results = new Array(promises.length);
    let completed = 0;

    if (promises.length === 0) return resolve([]);

    promises.forEach((p, index) => {
      Promise.resolve(p).then( // Promise.resolve() handles non-promise values too
        (value) => {
          results[index] = value; // store at the ORIGINAL index — order matters even
                                    // though promises can resolve out of order
          completed++;
          if (completed === promises.length) resolve(results);
        },
        (err) => reject(err) // reject immediately on first failure
      );
    });
  });
}

// Test
promiseAll([
  Promise.resolve(1),
  new Promise(res => setTimeout(() => res(2), 100)),
  3, // non-promise values are allowed too
]).then(console.log); // [1, 2, 3] after ~100ms, in correct order
```
**Complexity**: O(n) promises tracked concurrently. Key insight interviewers look for: storing
results by **index**, not push order, since promises can settle in any order.

### Challenge 6: Implement `curry`

**Problem**: Write a generic `curry(fn)` that transforms any function into its curried form,
supporting partial application with any grouping of arguments.

```js
function curry(fn) {
  return function curried(...args) {
    if (args.length >= fn.length) {
      return fn.apply(this, args);
    }
    return (...moreArgs) => curried.apply(this, [...args, ...moreArgs]);
  };
}

// Test
function add3(a, b, c) { return a + b + c; }
const curriedAdd = curry(add3);
console.log(curriedAdd(1)(2)(3));   // 6
console.log(curriedAdd(1, 2)(3));   // 6
console.log(curriedAdd(1)(2, 3));   // 6
console.log(curriedAdd(1, 2, 3));   // 6
```
**Complexity**: O(1) overhead per call level. Key insight: `fn.length` gives the declared
arity (number of named parameters) of the original function, which is how `curried` knows
when enough arguments have accumulated to actually invoke `fn`.

### Challenge 7: Flatten a Nested Array

**Problem**: Write `flatten(arr, depth = Infinity)` that flattens nested arrays to the given
depth, without using the built-in `Array.prototype.flat`.

```js
function flatten(arr, depth = Infinity) {
  if (depth < 1) return arr.slice();
  return arr.reduce((acc, item) => {
    if (Array.isArray(item)) {
      acc.push(...flatten(item, depth - 1));
    } else {
      acc.push(item);
    }
    return acc;
  }, []);
}

// Test
console.log(flatten([1, [2, [3, [4, 5]], 6]]));       // [1, 2, 3, 4, 5, 6]
console.log(flatten([1, [2, [3, [4, 5]], 6]], 1));    // [1, 2, [3, [4, 5]], 6]
```
**Complexity**: O(n) where n = total number of elements across all nesting levels.
**Iterative follow-up** (avoids recursion/call-stack limits for extremely deeply nested
input) using an explicit stack:
```js
function flattenIterative(arr) {
  const stack = [...arr];
  const result = [];
  while (stack.length) {
    const next = stack.shift();
    if (Array.isArray(next)) stack.unshift(...next);
    else result.push(next);
  }
  return result;
}
```

### Challenge 8: Implement `memoize`

**Problem**: Write a generic `memoize(fn)` that caches results by argument list, so repeated
calls with the same arguments return instantly from cache.

```js
function memoize(fn, resolver) {
  const cache = new Map();
  return function (...args) {
    const key = resolver ? resolver(...args) : JSON.stringify(args);
    if (cache.has(key)) return cache.get(key);
    const result = fn.apply(this, args);
    cache.set(key, result);
    return result;
  };
}

// Test
let calls = 0;
const slowSquare = memoize((n) => { calls++; return n * n; });
slowSquare(5); slowSquare(5); slowSquare(5);
console.log(calls); // 1 — only computed once, subsequent calls hit the cache
```
**Complexity**: O(1) cache lookup (after the O(k) cost of building the key from k arguments).
**Discussion point**: `JSON.stringify` as a default key resolver fails for arguments containing
functions, `undefined`, circular references, or where object key order varies — a custom
`resolver` function is the escape hatch for those cases, and is a natural interviewer
follow-up ("what if the arguments are objects — does this still work?").

### Challenge 9: Implement an LRU (Least Recently Used) Cache

**Problem**: Design a cache with `get(key)` and `put(key, value)`, fixed capacity, evicting
the least-recently-used entry when full. Both operations should be O(1).

```js
class LRUCache {
  #capacity;
  #map; // JS Map preserves insertion order, which we exploit for recency tracking

  constructor(capacity) {
    this.#capacity = capacity;
    this.#map = new Map();
  }

  get(key) {
    if (!this.#map.has(key)) return -1;
    const value = this.#map.get(key);
    this.#map.delete(key);   // re-insert to mark as MOST recently used
    this.#map.set(key, value);
    return value;
  }

  put(key, value) {
    if (this.#map.has(key)) this.#map.delete(key); // remove old position first
    else if (this.#map.size >= this.#capacity) {
      const oldestKey = this.#map.keys().next().value; // Map iterates in insertion order,
      this.#map.delete(oldestKey);                       // so the first key IS the least-recently-used
    }
    this.#map.set(key, value);
  }
}

// Test
const cache = new LRUCache(2);
cache.put(1, 'a');
cache.put(2, 'b');
console.log(cache.get(1));  // 'a' (and marks 1 as most-recently-used)
cache.put(3, 'c');           // capacity exceeded, evicts key 2 (least recently used)
console.log(cache.get(2));  // -1 (evicted)
console.log(cache.get(3));  // 'c'
```
**Complexity**: O(1) for both `get` and `put`, exploiting the fact that a native `Map`
maintains insertion order and offers O(1) delete/re-insert — a much simpler implementation
than the classic "doubly linked list + hash map" approach usually needed in languages without
an order-preserving hash map built in.

### Challenge 10: Array Chunking

**Problem**: Write `chunk(arr, size)` that splits an array into sub-arrays of the given size.

```js
function chunk(arr, size) {
  if (size <= 0) throw new Error('size must be positive');
  const result = [];
  for (let i = 0; i < arr.length; i += size) {
    result.push(arr.slice(i, i + size));
  }
  return result;
}

// Test
console.log(chunk([1,2,3,4,5,6,7], 3)); // [[1,2,3],[4,5,6],[7]]
```
**Complexity**: O(n). A very common "warm-up" question used to see baseline array-manipulation
comfort before moving to harder problems.

### Challenge 11: Implement a Simple Pub-Sub / Observable

**Problem**: Build a minimal `Observable`-style store: `subscribe(listener)` returns an
unsubscribe function, and `notify(data)` calls every current subscriber.

```js
function createStore(initialState) {
  let state = initialState;
  const listeners = new Set();

  return {
    getState: () => state,
    setState(update) {
      state = typeof update === 'function' ? update(state) : { ...state, ...update };
      listeners.forEach(listener => listener(state));
    },
    subscribe(listener) {
      listeners.add(listener);
      return () => listeners.delete(listener); // unsubscribe function — a common React
                                                 // useEffect cleanup-function shape
    },
  };
}

// Test
const store = createStore({ count: 0 });
const unsubscribe = store.subscribe(state => console.log('State changed:', state));
store.setState(s => ({ count: s.count + 1 })); // logs "State changed: { count: 1 }"
unsubscribe();
store.setState(s => ({ count: s.count + 1 })); // no log — unsubscribed
```
**Complexity**: O(1) subscribe/unsubscribe (`Set`), O(k) notify where k = active subscriber
count. This is essentially a minimal Redux store — recognizing that connection is a strong
signal in interviews ("this looks like Redux's core — can you explain the similarity?").

### Challenge 12: Implement a Simplified Virtual DOM Diff

**Problem**: Given two simple virtual node trees (`{ type, props, children }`), compute a
minimal list of patches to transform the old tree into the new one — illustrating the core
idea behind React's reconciliation (Part 7.1), not a production algorithm.

```js
function diff(oldNode, newNode) {
  const patches = [];
  walk(oldNode, newNode, patches, []);
  return patches;
}

function walk(oldNode, newNode, patches, path) {
  if (!oldNode && newNode) {
    patches.push({ type: 'CREATE', path, node: newNode });
    return;
  }
  if (oldNode && !newNode) {
    patches.push({ type: 'REMOVE', path });
    return;
  }
  if (oldNode.type !== newNode.type) {
    patches.push({ type: 'REPLACE', path, node: newNode });
    return;
  }
  const propPatches = diffProps(oldNode.props, newNode.props);
  if (Object.keys(propPatches).length > 0) {
    patches.push({ type: 'PROPS', path, props: propPatches });
  }
  const maxLen = Math.max(oldNode.children?.length || 0, newNode.children?.length || 0);
  for (let i = 0; i < maxLen; i++) {
    walk(oldNode.children?.[i], newNode.children?.[i], patches, [...path, i]);
  }
}

function diffProps(oldProps = {}, newProps = {}) {
  const changed = {};
  for (const key of new Set([...Object.keys(oldProps), ...Object.keys(newProps)])) {
    if (oldProps[key] !== newProps[key]) changed[key] = newProps[key] ?? null;
  }
  return changed;
}

// Test
const oldTree = { type: 'div', props: { className: 'a' }, children: [{ type: 'span', props: {}, children: [] }] };
const newTree = { type: 'div', props: { className: 'b' }, children: [{ type: 'p', props: {}, children: [] }] };
console.log(diff(oldTree, newTree));
// [{ type: 'PROPS', path: [], props: { className: 'b' } },
//  { type: 'REPLACE', path: [0], node: { type: 'p', ... } }]
```
**Discussion point**: real React additionally uses the `key` prop (Part 7.7) to correctly
match reordered list children instead of naively diffing by index position — without keys, a
reordered list produces a wave of unnecessary REPLACE/PROPS patches instead of recognizing
items simply moved, exactly the bug class Part 7.7's key-related questions test.

## 14.9 Behavioral & Interview-Process Tips

Frontend interviews at most companies span 3-5 rounds: a recruiter screen, a coding round
(often the challenges in 14.8 or a small feature-build), a system design round (Part 13), a
"deep dive"/trivia round drawing on Parts 1-12, and a behavioral round. A few practical notes:

- **Think out loud during coding rounds.** Interviewers are evaluating your process, not just
  the final answer — narrate your approach, mention tradeoffs, and ask clarifying questions
  ("should this handle negative numbers?", "what should happen on an empty array?") before
  diving into code. Silence for 10 minutes followed by a perfect solution scores *worse* in
  most rubrics than audible reasoning that arrives at a slightly rougher solution.
- **Start with a naive/brute-force solution out loud, then optimize** — this shows you
  understand the problem completely before optimizing, and gives the interviewer a fallback
  if you run out of time on the optimal approach.
- **Always discuss complexity** (time/space Big-O) once you have working code — even for
  "soft" frontend questions like "implement debounce," being able to say "O(1) per call, O(1)
  extra space for the closure variables" signals rigor.
- **For system design rounds** (Part 13), spend the first 5 minutes purely on clarifying
  requirements before writing/drawing anything — jumping straight to a solution without
  clarifying scope is one of the most common ways strong candidates lose points.
- **Behavioral questions** ("tell me about a time you disagreed with a teammate," "tell me
  about a project you're proud of") are best answered with the **STAR method**: Situation,
  Task, Action, Result — a specific, concrete story beats a general philosophy every time.
  Prepare 4-6 STAR stories in advance covering: a technical challenge you solved, a
  disagreement you navigated, a time you had to learn something new quickly, a mistake you
  made and what you learned, a time you improved a process/system beyond your immediate task,
  and a time you helped a teammate.
- **Ask genuine questions back** at the end of every round — about the team's frontend stack,
  how they approach code review, what a recent hard bug/incident looked like. It signals real
  interest and gives you real signal about whether you'd want the job.
- **It's fine to say "I don't know, but here's how I'd find out"** for a genuinely unfamiliar
  topic — bluffing confidently through a wrong answer scores far worse than honest, structured
  uncertainty followed by a reasonable plan to investigate.
- **Practice explaining Part 4's JS fundamentals (closures, `this`, the event loop) out loud
  to another person or a rubber duck** — these show up, in some form, in nearly every frontend
  interview regardless of the specific framework the company uses, because they're
  framework-agnostic signals of real understanding.

## 14.10 Rapid-Fire Q&A Round (Quick Review)

Use this section as a final speed-drill before an interview — cover the answer and see if you
can produce it from the question alone.

1. **Q: What does `box-sizing: border-box` change?** A: `width`/`height` include padding and
   border, not just content (Part 3.1).
2. **Q: What triggers a new CSS stacking context?** A: `position: fixed/sticky`,
   `opacity < 1`, `transform`, `filter`, and others (Part 14.1 Q14).
3. **Q: What's the difference between `let` and `const`?** A: Both block-scoped; `const`
   bindings can't be reassigned (Part 4.2).
4. **Q: Name the 8 falsy values.** A: `false, 0, -0, 0n, "", null, undefined, NaN` (Part 4.1).
5. **Q: What does `Array.prototype.reduce` do?** A: Folds an array into a single accumulated
   value via a callback `(acc, item) => newAcc` (Part 4.6).
6. **Q: What's a pure function?** A: Same input always produces the same output, with no
   observable side effects (no mutating external state, no I/O).
7. **Q: What does `Object.is(NaN, NaN)` return, vs `NaN === NaN`?** A: `Object.is` returns
   `true`; `===` returns `false` — `Object.is` uses the SameValue algorithm, which correctly
   treats `NaN` as equal to itself (Part 4.1).
8. **Q: What is "referential transparency"?** A: An expression can be replaced with its
   evaluated value without changing program behavior — a property of pure functions.
9. **Q: What does `Array.isArray([])` check that `typeof [] === 'object'` cannot
   distinguish?** A: Whether a value is specifically an array vs. a plain object — both
   report `typeof === 'object'` (Part 4.1).
10. **Q: What is a "stale closure" bug in React?** A: A `useEffect`/callback capturing an old
    value of a prop/state variable because it wasn't included in the dependency array
    (Part 7.4).
11. **Q: What's the difference between `Map` and a plain object as a key-value store?** A:
    `Map` keys can be any value (including objects/functions), preserves insertion order
    reliably, has a `.size` property, and doesn't inherit prototype properties that could
    collide with string keys.
12. **Q: What does `Array.prototype.flatMap` do?** A: Equivalent to `.map(fn).flat(1)` in one
    pass — maps each element then flattens one level.
13. **Q: What's the difference between `Object.keys`, `Object.values`, `Object.entries`?** A:
    Return arrays of a plain object's own enumerable keys, values, or `[key, value]` pairs
    respectively.
14. **Q: What does the `key` prop do in a React list, in one sentence?** A: Tells React which
    array item is which across renders so it can correctly preserve/re-associate state and DOM
    nodes (Part 7.7).
15. **Q: What is "props drilling"?** A: Passing a prop down through many intermediate
    components that don't use it themselves, purely to reach a deeply nested descendant
    (Part 7.8).
16. **Q: What does `useMemo` memoize, vs `useCallback`?** A: `useMemo` memoizes a computed
    **value**; `useCallback` memoizes a **function reference** (Part 7.5).
17. **Q: Name two things `React.memo` cannot fix.** A: A prop that's a new object/array/
    function reference every render even with identical contents (needs `useMemo`/
    `useCallback` upstream), and a component consuming a Context that changes (Part 7.7,
    Part 7.8).
18. **Q: What is "hydration" in the context of SSR?** A: The client attaching event listeners/
    state to server-rendered HTML already present in the DOM, instead of re-creating it
    (Part 7.12).
19. **Q: What does `aria-live="polite"` do?** A: Announces dynamic content changes to screen
    readers without stealing focus (Part 2.8, Part 12.4).
20. **Q: What is `:focus-visible` for?** A: Shows a focus ring specifically for keyboard/
    non-pointer navigation, keeping mouse-driven UI visually clean while never breaking
    keyboard accessibility (Part 12.3).
21. **Q: What does WCAG's "AA" conformance level generally require for text contrast?** A: At
    least 4.5:1 for normal text, 3:1 for large text (Part 12.5).
22. **Q: What's the difference between unit, integration, and E2E tests?** A: Unit tests
    isolated small units (pure functions/hooks); integration/component tests render real
    components with mocked network; E2E tests drive a real browser against the real running
    app (Part 10.1).
23. **Q: Why prefer `getByRole` over `getByTestId` in React Testing Library?** A: It matches
    how a real user/assistive technology perceives the UI, and implicitly validates
    accessibility; `data-testid` has no real user-facing meaning (Part 10.3).
24. **Q: What does `npm ci` do differently from `npm install`?** A: Installs exactly what's in
    the lockfile (deterministic, fails if `package.json`/lockfile are out of sync) — the
    correct choice for CI pipelines (Part 9.1).
25. **Q: Why is Vite's dev server faster to start than a traditional Webpack dev server on
    large projects?** A: It serves source files directly as native ES modules without a full
    upfront bundling step, transpiling on-demand per requested file (Part 9.2).
26. **Q: What's the difference between `preload` and `prefetch` link hints?** A: `preload` is
    for a resource needed immediately on the current page; `prefetch` is for a resource likely
    needed on the *next* navigation (Part 11.3).
27. **Q: What does `fetchpriority="high"` do?** A: Hints to the browser to prioritize
    downloading that specific resource (commonly the LCP image) earlier relative to other
    resources (Part 11.1).
28. **Q: What is "layout thrashing," in one sentence?** A: Interleaving DOM reads and writes
    in a loop, forcing repeated synchronous layout recalculation (Part 6.5).
29. **Q: What does `requestAnimationFrame` guarantee that `setTimeout(fn, 16)` does not?** A:
    Execution timed to right before the browser's next actual repaint, synced to display
    refresh rate — `setTimeout` has no such synchronization and can cause uneven frame timing
    (Part 6.7).
30. **Q: What is GSAP's `stagger.from: 'center'` option used for?** A: Making a staggered
    animation ripple outward from the center of a group of elements instead of strictly
    left-to-right/first-to-last (Part 8.5).
31. **Q: Why does ScrollTrigger need `markers: true` during development?** A: To visually see
    exactly where the computed start/end trigger points land on screen, since the
    two-part `"trigger-position viewport-position"` syntax is easy to miscalculate mentally
    (Part 8.6).
32. **Q: What does `gsap.context().revert()` clean up?** A: Kills all tweens/timelines created
    within that context and removes any ScrollTrigger instances created inside it, restoring
    original inline styles (Part 8.7).
33. **Q: What's the risk of leaving `will-change` applied permanently on many elements?** A:
    Each promoted compositor layer consumes GPU memory continuously, which can hurt
    performance rather than help once overused (Part 3.6, 8.11).
34. **Q: What does `AnimatePresence` enable in Framer Motion that plain conditional rendering
    cannot?** A: Exit animations — keeping a component mounted just long enough to play its
    `exit` variant before actually unmounting it (Part 8.8).
35. **Q: In the FLIP technique, what does "Invert" actually compute?** A: The transform
    (translate + scale) needed to make the element visually appear at its First
    position/size, even though it's now laid out at its Last position/size (Part 8.10).
36. **Q: What's the key difference between SSE and WebSockets?** A: SSE is one-directional
    (server→client only); WebSockets are full-duplex (either side can send anytime)
    (Part 13.6).
37. **Q: Why is offset-based pagination risky for a frequently-changing feed?** A: Items
    inserted/removed between page loads can cause skipped or duplicated results; cursor-based
    pagination avoids this by anchoring to a specific item (Part 13.3).
38. **Q: What is "optimistic UI update"?** A: Updating the UI immediately as if a mutation
    succeeded, before the server confirms, with a rollback path if it actually fails —
    trades a small risk of a visible correction for a much faster perceived response
    (Part 13.5).
39. **Q: What does `structuredClone()` handle that `JSON.parse(JSON.stringify(x))` does
    not?** A: `Date` objects, `Map`/`Set`, circular references, and `undefined` values —
    without silently corrupting or dropping them (Part 14.2 Q18).
40. **Q: What is the "Rules of Hooks" violation risk of calling a hook inside an `if`
    statement?** A: It can change the *order* of hook calls between renders, corrupting
    React's internal per-component state bookkeeping, which relies on call order rather than
    hook names (Part 7.6).

# Part 15 — Cheat Sheets, Glossary, Study Roadmap & Closing Notes

## 15.1 CSS Cheat Sheet

### Selectors & Specificity Quick Reference

| Selector | Example | Specificity weight |
|---|---|---|
| Universal | `*` | 0,0,0 |
| Element/pseudo-element | `div`, `::before` | 0,0,1 |
| Class/attribute/pseudo-class | `.card`, `[type=text]`, `:hover` | 0,1,0 |
| ID | `#header` | 1,0,0 |
| Inline style | `style=""` | beats all of the above |
| `!important` | any declaration | beats everything in normal cascade |

### Flexbox Properties Quick Reference

| Property (on container) | Values |
|---|---|
| `display` | `flex`, `inline-flex` |
| `flex-direction` | `row` (default), `row-reverse`, `column`, `column-reverse` |
| `justify-content` | `flex-start`, `flex-end`, `center`, `space-between`, `space-around`, `space-evenly` |
| `align-items` | `stretch` (default), `flex-start`, `flex-end`, `center`, `baseline` |
| `flex-wrap` | `nowrap` (default), `wrap`, `wrap-reverse` |
| `gap` | any length, e.g. `16px` |

| Property (on item) | Values |
|---|---|
| `flex-grow` | number, share of extra space (default 0) |
| `flex-shrink` | number, share of shrinkage (default 1) |
| `flex-basis` | length or `auto` |
| `flex` | shorthand: `grow shrink basis` |
| `align-self` | overrides container's `align-items` for one item |
| `order` | number, visual reordering without changing DOM order |

### Grid Properties Quick Reference

| Property | Purpose |
|---|---|
| `grid-template-columns`/`rows` | define track sizes, e.g. `1fr 2fr`, `repeat(3, 1fr)` |
| `grid-template-areas` | named layout regions as ASCII-art strings |
| `gap` (`row-gap`/`column-gap`) | spacing between tracks |
| `grid-column`/`grid-row` | placement/span, e.g. `span 2` |
| `place-items` | shorthand for `align-items` + `justify-items` |
| `minmax(min, max)` | a track that's never smaller/larger than given bounds |
| `repeat(auto-fill\|auto-fit, minmax(...))` | responsive column count with zero media queries |

### Positioning Quick Reference

| Value | Removed from flow? | Positioned relative to |
|---|---|---|
| `static` | No | N/A (default) |
| `relative` | No | Its own normal-flow position |
| `absolute` | Yes | Nearest positioned ancestor (or viewport) |
| `fixed` | Yes | Viewport, ignores scroll |
| `sticky` | No (until threshold), then acts fixed | Its containing block, within scroll range |

### Units Quick Reference

| Unit | Relative to |
|---|---|
| `px` | Absolute |
| `%` | Parent's corresponding dimension |
| `em` | Current element's font-size (compounds when nested) |
| `rem` | Root (`<html>`) font-size |
| `vw`/`vh` | 1% of viewport width/height |
| `dvh`/`svh`/`lvh` | Dynamic/small/large viewport height (mobile-chrome-safe) |
| `fr` | A fraction of remaining space in a Grid track list |

### Performance-Safe Animation Properties

| Property | Compositor-only (cheap)? |
|---|---|
| `transform` | Yes |
| `opacity` | Yes |
| `width`/`height`/`top`/`left`/`margin` | No — triggers layout |
| `color`/`background`/`box-shadow` | No — triggers paint (but not layout) |

## 15.2 JavaScript Cheat Sheet

### Type Coercion Quick Reference

| Expression | Result |
|---|---|
| `0 == '0'` | `true` |
| `0 == ''` | `true` |
| `null == undefined` | `true` |
| `NaN == NaN` | `false` |
| `[] == false` | `true` |
| `typeof null` | `'object'` |
| `typeof undefined` | `'undefined'` |
| `typeof NaN` | `'number'` |
| `Array.isArray([])` | `true` |

### Array Methods Quick Reference

| Method | Mutates original? | Returns |
|---|---|---|
| `.map(fn)` | No | New array of transformed items |
| `.filter(fn)` | No | New array of matching items |
| `.reduce(fn, init)` | No | Single accumulated value |
| `.forEach(fn)` | No | `undefined` (side effects only) |
| `.find(fn)` | No | First matching element or `undefined` |
| `.some(fn)`/`.every(fn)` | No | Boolean |
| `.sort(fn)` | **Yes** | Same array, sorted |
| `.reverse()` | **Yes** | Same array, reversed |
| `.splice(...)` | **Yes** | Removed elements |
| `.slice(start, end)` | No | New array (shallow copy of range) |
| `.push`/`.pop`/`.shift`/`.unshift` | **Yes** | New length / removed element |
| `.flat(depth)` | No | New flattened array |
| `.includes(val)` | No | Boolean (uses SameValueZero, handles `NaN` correctly) |

### Event Loop Priority Quick Reference

```
1. Run all synchronous code (call stack) to completion.
2. Drain the ENTIRE microtask queue (Promise .then/.catch/.finally, queueMicrotask).
3. Run exactly ONE macrotask (setTimeout/setInterval/DOM event/I/O callback).
4. Repeat from step 2.
```

### `this` Binding Priority Quick Reference

```
1. new Fn()                     -> this = new instance
2. fn.call(obj)/.apply(obj)/.bind(obj)() -> this = obj
3. obj.method()                 -> this = obj (whatever is left of the dot)
4. fn()                         -> this = undefined (strict) / global object (sloppy)
5. Arrow functions ignore ALL of the above -> this = lexically enclosing scope, forever
```

### Promise Combinator Quick Reference

| Method | Settles when | Rejects when |
|---|---|---|
| `Promise.all` | All resolve | Any one rejects (immediately) |
| `Promise.allSettled` | All settle (success or failure) | Never rejects |
| `Promise.race` | First one settles (either way) | If that first one rejects |
| `Promise.any` | First one fulfills | Only if ALL reject |

## 15.3 TypeScript Cheat Sheet

### Utility Types Quick Reference

| Utility | Effect |
|---|---|
| `Partial<T>` | All properties optional |
| `Required<T>` | All properties required |
| `Readonly<T>` | All properties read-only |
| `Pick<T, K>` | Only keys `K` from `T` |
| `Omit<T, K>` | All keys from `T` except `K` |
| `Record<K, V>` | Object type with keys `K`, values `V` |
| `ReturnType<F>` | Return type of function type `F` |
| `Parameters<F>` | Tuple of parameter types of `F` |
| `NonNullable<T>` | Removes `null`/`undefined` from `T` |
| `Exclude<T, U>` | Removes members of union `T` assignable to `U` |
| `Extract<T, U>` | Keeps only members of union `T` assignable to `U` |

### `any` vs `unknown` vs `never` Quick Reference

| Type | Can assign anything to it? | Can use it without narrowing? | Represents |
|---|---|---|---|
| `any` | Yes | Yes (unsafely) | "Opt out of type checking" |
| `unknown` | Yes | No — must narrow first | "Safely unknown value" |
| `never` | No (except from `never` itself) | N/A | "This can never happen" (e.g. exhaustive switch default, function that always throws) |

### `interface` vs `type` Quick Reference

| Feature | `interface` | `type` |
|---|---|---|
| Object shapes | Yes | Yes |
| Declaration merging | Yes | No |
| Unions (`A \| B`) | No | Yes |
| Tuples | No | Yes |
| Mapped/conditional types | No | Yes |
| Extending | `extends` | `&` (intersection) |

## 15.4 React Cheat Sheet

### Hooks Quick Reference

| Hook | Purpose | Re-renders on change? |
|---|---|---|
| `useState` | Local component state | Yes |
| `useEffect` | Side effects after render/commit | N/A (runs after render, doesn't itself cause one) |
| `useLayoutEffect` | Side effects synchronously before paint | N/A, blocks paint until it finishes |
| `useRef` | Mutable value/DOM reference persisting across renders | No |
| `useContext` | Read a value from a Provider higher up | Yes, whenever the context value changes |
| `useReducer` | Complex state logic via actions | Yes |
| `useMemo` | Memoize an expensive computed value | Recomputes only when deps change |
| `useCallback` | Memoize a function reference | New reference only when deps change |
| `useId` | Stable unique ID, SSR-safe | No |
| `useTransition` | Mark a state update as non-urgent (lets urgent updates interrupt it) | Yes, but deprioritized |
| `useDeferredValue` | Get a "lagging" version of a fast-changing value for expensive renders | Yes, but deferred |
| `useSyncExternalStore` | Subscribe to an external (non-React) data store safely | Yes, on store change |

### `useEffect` Dependency Array Quick Reference

| Dependency array | Effect timing |
|---|---|
| Omitted entirely | Runs after **every** render |
| `[]` | Runs **once**, after initial mount only |
| `[a, b]` | Runs after mount, and again whenever `a` or `b` changes |
| Cleanup function returned | Runs before the next effect execution, and once more on unmount |

### Component Re-render Triggers

| Trigger | Causes re-render? |
|---|---|
| Component's own state changes (`setState`) | Yes |
| Parent re-renders | Yes, by default, for every child (unless wrapped in `React.memo` with unchanged shallow props) |
| Consumed context value changes | Yes, for every consumer regardless of memoization |
| Props change (shallow-different) | Yes |
| Props reference changes but content is "the same" (new object/array/function each render) | Yes — `React.memo`'s shallow comparison sees a new reference as different |

### Common React Anti-Patterns Quick Reference

| Anti-pattern | Why it's a problem | Fix |
|---|---|---|
| Using array index as `key` in a reorderable list | Misassociates state/DOM across reorders | Use a stable unique ID from the data |
| Mutating state directly (`state.push(x)`) | React can't detect the change (same reference) | Create a new array/object (`[...state, x]`) |
| Missing `useEffect` cleanup for subscriptions/timers | Memory leaks, "update on unmounted component" warnings | Return a cleanup function from the effect |
| Wrapping everything in `useMemo`/`useCallback` reflexively | Adds overhead with no real benefit most of the time | Only memoize genuinely expensive computations or values passed to memoized children |
| Storing derived data in state instead of computing it during render | Two sources of truth can drift out of sync | Compute derived values directly in the render body (or `useMemo` if expensive) |
| Fetching data directly in the component body without an effect/library | Runs on every render, uncontrolled | Use `useEffect` + cleanup, or better, a data-fetching library (TanStack Query) |
| Deeply nested prop drilling | Hard to maintain, brittle refactors | `useContext` for a few levels, a state library for broad/frequent sharing |

## 15.5 GSAP & Animation Cheat Sheet

### Core Tween Methods Quick Reference

| Method | Animates from | Animates to |
|---|---|---|
| `gsap.to(target, vars)` | Current/CSS state | `vars` values |
| `gsap.from(target, vars)` | `vars` values | Current/CSS state |
| `gsap.fromTo(target, fromVars, toVars)` | `fromVars` (explicit) | `toVars` (explicit) |
| `gsap.set(target, vars)` | N/A (instant) | `vars` values, no animation |

### Easing Quick Reference

| Ease | Feel |
|---|---|
| `power1`/`power2`/`power3.out` | Fast start, slow finish — standard entrances |
| `power2.in` | Slow start, fast finish — standard exits |
| `power2.inOut` | Slow-fast-slow — continuous/looping motion |
| `back.out(1.7)` | Overshoots then settles — playful emphasis |
| `elastic.out(1, 0.3)` | Springy oscillation before settling |
| `bounce.out` | Simulates a physical bounce |
| `none`/`linear` | Constant speed — correct for scroll-scrubbed animation |

### ScrollTrigger Options Quick Reference

| Option | Purpose |
|---|---|
| `trigger` | Element that determines when the animation activates |
| `start`/`end` | `"<trigger-position> <viewport-position>"`, e.g. `"top 80%"` |
| `scrub` | Ties animation progress directly to scroll (`true` or a smoothing-seconds number) |
| `pin` | Freezes the trigger element in place while its section scrolls past |
| `toggleActions` | `"onEnter onLeave onEnterBack onLeaveBack"`, e.g. `"play none none reverse"` |
| `markers` | Debug-only visual start/end indicators — remove before production |

### GSAP + React Cleanup Quick Reference

| Approach | Cleanup mechanism |
|---|---|
| `useGSAP` (from `@gsap/react`) | Automatic — reverts all tweens/ScrollTriggers created inside on unmount/dep change |
| Manual `useEffect` + `gsap.context()` | Call `ctx.revert()` in the effect's cleanup function |
| Raw `useEffect` with no context | Manual `.kill()` calls needed on every tween/ScrollTrigger — error-prone, avoid |

## 15.6 Glossary — Key Terms Explained

**Bundler**: A build tool (Vite, Webpack, Rollup, esbuild) that resolves your module import
graph and combines it into optimized output files, handling minification, tree-shaking, and
code splitting along the way.

**CDN (Content Delivery Network)**: A geographically distributed network of servers that
caches and serves static assets (JS, CSS, images) from a location physically close to each
user, reducing latency compared to a single origin server.

**Closure**: A function bundled together with references to its surrounding lexical scope,
allowing it to "remember" and access those variables even after the outer function has
finished executing. The foundation of private state, memoization, and debounce/throttle
implementations in JavaScript.

**Compositor thread**: A separate browser thread (distinct from the main JS/layout/paint
thread) responsible for combining already-painted layers into the final on-screen frame.
Animations limited to `transform`/`opacity` can run entirely here, bypassing the more
expensive main-thread layout/paint steps.

**CORS (Cross-Origin Resource Sharing)**: A browser security mechanism that restricts
JavaScript running on one origin (scheme+host+port) from making requests to a different
origin unless that origin explicitly opts in via response headers, preventing malicious sites
from silently reading data from other sites on a user's behalf.

**CSR (Client-Side Rendering)**: A rendering strategy where the server sends a minimal HTML
shell and a JS bundle, and the browser builds the entire visible UI by executing that JS.

**CSSOM (CSS Object Model)**: The browser's in-memory tree representation of all applicable
CSS rules, built in parallel with the DOM and combined with it to form the render tree.

**Debounce**: A technique that delays invoking a function until a specified quiet period has
passed since the last time it was requested to run — used for search-as-you-type, resize
handlers, and auto-save features.

**Declaration merging**: A TypeScript feature where multiple `interface` declarations with
the same name are automatically combined into one, allowing you to extend an existing
interface (including ones from external libraries) without modifying its original source.

**Declarative programming**: Describing *what* the result should look like given the current
data (e.g., React's JSX), as opposed to imperative programming, which specifies the exact
step-by-step instructions to produce that result (e.g., manual `document.createElement` calls).

**Event bubbling**: The phase of DOM event propagation where an event travels from the
target element back up through each of its ancestors, allowing a single listener on a common
ancestor to handle events from many descendants (event delegation).

**Event delegation**: A pattern of attaching one listener to a stable parent element instead
of many listeners to individual children, relying on event bubbling and inspecting
`event.target` to determine which specific descendant triggered the event.

**Event loop**: The mechanism that allows JavaScript's single thread to handle asynchronous
operations by continuously checking the call stack, then the microtask queue, then the
macrotask queue, executing work from each in a defined priority order.

**FLIP (First, Last, Invert, Play)**: An animation technique for smoothly transitioning
between two layout states by measuring the "before" and "after" bounding boxes, computing the
transform needed to visually bridge them, and animating only that cheap transform instead of
expensive layout properties.

**Function component**: A React component defined as a plain JavaScript function that
returns JSX, using Hooks for state and lifecycle behavior — the modern default, replacing
class components for nearly all new code.

**Generics (TypeScript)**: A way to write functions, classes, or types that work across a
range of types while preserving the specific type relationships between inputs and outputs,
without resorting to `any`.

**Hoisting**: JavaScript's behavior of processing variable and function declarations before
executing code line by line — `var` declarations and function declarations are hoisted to the
top of their scope; `let`/`const` are hoisted but remain inaccessible (the "Temporal Dead
Zone") until their actual declaration line runs.

**Hydration**: The process by which a client-side JavaScript framework attaches event
listeners and internal state to server-rendered HTML that's already present in the DOM,
rather than re-creating that DOM from scratch.

**Idempotent**: An operation that produces the same result no matter how many times it's
applied — an important property for retriable network requests (e.g., a `PUT` request is
typically idempotent; a `POST` that creates a new resource typically is not).

**INP (Interaction to Next Paint)**: A Core Web Vital measuring the time from a user
interaction (click, tap, key press) to the next visual update on screen, reflecting overall
page responsiveness throughout its lifetime, not just on load.

**IntersectionObserver**: A browser API that efficiently detects when an element enters or
exits the viewport (or another ancestor), without the performance cost of polling scroll
position manually.

**JSX**: A syntax extension for JavaScript that resembles HTML, compiled by tools like
Babel/SWC into plain function calls (`React.createElement` or the modern JSX runtime
equivalent) that build a tree of plain JavaScript objects describing the desired UI.

**Layout (reflow)**: The browser's process of computing the exact size and position of every
element on the page, triggered by changes to geometry-affecting properties or by reading
certain layout properties immediately after a style change.

**Layout thrashing**: A performance anti-pattern caused by interleaving DOM reads and writes
in a loop, forcing the browser to perform many repeated, synchronous layout recalculations
instead of batching the work.

**LCP (Largest Contentful Paint)**: A Core Web Vital measuring the time until the largest
visible content element (usually a hero image, video poster, or heading) finishes rendering.

**Lexical scope**: The scope determined by where a function or variable is physically written
in the source code, as opposed to where/how it's called — this is what closures and arrow
functions' `this` binding rely on.

**Long task**: Any block of main-thread JavaScript execution lasting longer than 50
milliseconds without yielding, which can delay the browser from responding to user input and
directly hurts INP.

**LRU (Least Recently Used) cache**: A cache eviction strategy that discards the
least-recently-accessed entry first when the cache reaches capacity, keeping frequently and
recently used data readily available.

**Memoization**: Caching the result of an expensive function call keyed by its arguments, so
subsequent calls with the same arguments return instantly from cache instead of recomputing.

**Microtask**: A task with higher priority than macrotasks in JavaScript's event loop —
promise callbacks (`.then`/`.catch`/`.finally`) and `queueMicrotask` calls — all pending
microtasks are fully drained before the engine processes the next macrotask.

**Optimistic update**: Updating the UI immediately as though a pending mutation has already
succeeded, before the server actually confirms it, providing a faster perceived response with
a rollback path if the mutation ultimately fails.

**POUR**: The four principles WCAG accessibility guidelines are organized around: Perceivable,
Operable, Understandable, Robust.

**Prop drilling**: Passing data down through multiple layers of intermediate components that
don't themselves use that data, purely to make it available to a deeply nested descendant.

**Prototype chain**: The series of internal links between JavaScript objects
(`[[Prototype]]`), used to resolve property lookups that aren't found directly on an object
itself — the mechanism underlying all inheritance in JavaScript, including `class` syntax.

**Reconciliation**: React's process of comparing a newly rendered virtual DOM tree against the
previous one and computing the minimal set of real DOM mutations required to update the
screen.

**Referential equality**: Comparing two values by whether they point to the exact same
location in memory (`===` for objects/arrays/functions), rather than by comparing their
contents — this is why two structurally-identical objects created separately are not `===`
equal to each other.

**Render-blocking resource**: A CSS or JavaScript resource that must finish downloading (and,
for synchronous scripts, executing) before the browser can continue rendering the page,
directly delaying first paint.

**Scrub (GSAP/ScrollTrigger)**: Tying an animation's playback progress directly to the user's
scroll position, so scrolling forward and backward moves the animation forward and backward
in lockstep.

**SSG (Static Site Generation)**: A rendering strategy where HTML is generated once at build
time (not per request) and served as-is, ideal for content that's identical for every visitor.

**SSR (Server-Side Rendering)**: A rendering strategy where the server executes framework
rendering code on every request to produce full HTML, which the browser then hydrates into an
interactive application.

**Stale-while-revalidate**: A caching strategy that serves cached data immediately for
perceived speed, then silently refetches fresh data in the background and updates the UI if
anything changed.

**Stacking context**: An independent, self-contained layering context for `z-index`
comparisons, created by certain CSS properties (e.g., `position: fixed`, `opacity < 1`,
`transform`), inside which child elements' `z-index` values are compared only against each
other, not against elements in sibling stacking contexts.

**Structural typing**: TypeScript's type-compatibility model, where two types are considered
compatible if they have the same shape (matching properties/methods), regardless of their
declared names — as opposed to nominal typing, where types are compatible only if explicitly
declared as related.

**Tree-shaking**: The process by which a bundler removes exported code that is never actually
imported anywhere in the application, relying on ES Modules' statically analyzable
import/export structure to prove safety.

**TDZ (Temporal Dead Zone)**: The period between entering a scope and a `let`/`const`
variable's actual declaration line, during which referencing that variable throws a
`ReferenceError`, even though it has technically already been hoisted.

**Throttle**: A technique that guarantees a function executes at most once per specified time
interval, regardless of how frequently it's requested to run — used for scroll/resize
handlers.

**Virtual DOM**: A lightweight, in-memory JavaScript object representation of the desired UI,
which React diffs against the previous version to compute the minimal real DOM changes needed.

**Virtualization (list)**: Rendering only the currently-visible subset of a long list (plus a
small buffer) rather than every item, recycling DOM nodes as the user scrolls, to keep
performance constant regardless of total list length.

**Web Component**: A browser-native way to build encapsulated, reusable custom HTML elements
using Custom Elements, Shadow DOM, and HTML Templates, without requiring any JavaScript
framework.

**WebSocket**: A persistent, full-duplex communication protocol allowing both client and
server to send messages to each other at any time over a single long-lived connection.

**XSS (Cross-Site Scripting)**: A security vulnerability where an attacker injects malicious
JavaScript into a page viewed by other users, most commonly by exploiting unsanitized
rendering of user-supplied content via `innerHTML` or similar APIs.

## 15.7 Study Roadmap — 10 Weeks From Basics to Interview-Ready

This roadmap assumes roughly 1.5-2 hours per day. Adjust pacing to your own schedule, but keep
the **order** — each week deliberately builds on the previous one's foundations, matching the
order of Parts 1-14 in this guide.

### Week 1 — HTML & CSS Foundations (Part 2, Part 3.1-3.5)
- **Day 1**: Read Part 2 in full. Build a single static page using only semantic tags
  (`header`, `nav`, `main`, `article`, `section`, `aside`, `footer`) — no `<div>` allowed
  except where truly nothing semantic fits.
- **Day 2**: Build a real HTML form with proper `<label>` associations, correct `type`
  attributes, `required`/`pattern` validation, and a `<fieldset>`/`<legend>` group. Test it
  with the keyboard only — mouse unplugged.
- **Day 3**: Read Part 3.1-3.2 (box model, cascade, specificity). Deliberately write two
  conflicting CSS rules and predict which wins before checking DevTools.
- **Day 4**: Read Part 3.3 (positioning). Build a dropdown menu using `position: relative` on
  the parent and `position: absolute` on the menu.
- **Day 5**: Read Part 3.4 (Flexbox). Rebuild a navbar, then a "pricing cards" row, using only
  Flexbox — no floats, no absolute positioning.
- **Day 6**: Read Part 3.5 (Grid). Rebuild the same page's overall layout (sidebar + main +
  footer) using CSS Grid with named `grid-template-areas`.
- **Day 7**: Review. Re-read Part 14.1 (HTML/CSS Q&A) and answer every question from memory
  before checking the written answer.

### Week 2 — CSS Advanced, Responsive Design, JS Fundamentals Begin (Part 3.6-3.12, Part 4.1-4.2)
- **Day 1**: Read Part 3.6 (transforms/transitions/performance). Build a hover card effect
  using only `transform`/`opacity`, then inspect it in the Performance tab to confirm no
  layout/paint blocks appear.
- **Day 2**: Read Part 3.7-3.8 (keyframes, responsive design). Build a fluid, mobile-first
  layout using `clamp()` for typography and at least two `min-width` breakpoints.
- **Day 3**: Read Part 3.9-3.11 (custom properties, SASS, BEM). Refactor Week 1's page to use
  CSS custom properties for a light/dark theme toggle.
- **Day 4**: Read Part 3.12 (CSS-in-JS/Tailwind overview) for conceptual breadth — no need to
  build anything yet if you haven't chosen a framework.
- **Day 5**: Read Part 4.1 (types/coercion). Write out, from memory, the results of 10
  `==` comparisons before checking against Part 4.1's table.
- **Day 6**: Read Part 4.2 (scope/hoisting/TDZ). Type out the classic `var` vs `let` in a
  `setTimeout` loop example yourself and confirm you get `3,3,3` vs `0,1,2` as predicted.
- **Day 7**: Review Week 1-2. Rebuild one small page combining everything so far, entirely
  from memory, without referring back to the guide.

### Week 3 — JavaScript Core: Closures, `this`, Prototypes, Functions (Part 4.3-4.6)
- **Day 1**: Read Part 4.3 (closures). Implement a `makeCounter()` module-pattern function
  from scratch without looking at the example first, then compare.
- **Day 2**: Read Part 4.4 (`this`/call/apply/bind). Write three functions demonstrating each
  of the four `this`-binding rules, plus a fifth showing an arrow function ignoring all of
  them.
- **Day 3**: Read Part 4.5 (prototypes/classes). Build a small class hierarchy (`Animal` →
  `Dog`/`Cat`) using both `Object.create` directly and `class`/`extends`, and confirm they
  produce the same prototype chain via `Object.getPrototypeOf`.
- **Day 4**: Read Part 4.6 (functions deep dive, higher-order functions). Implement `.map`,
  `.filter`, and `.reduce` yourself from scratch using a plain `for` loop, to internalize what
  they're actually doing under the hood.
- **Day 5**: Practice: write 5 small functions using closures for realistic use cases
  (memoization, a simple counter, a rate limiter) without referring to Part 4.3's examples.
- **Day 6**: Attempt Part 14.8 Challenge 6 (curry) and Challenge 4 (EventEmitter) cold, before
  reading the provided solutions.
- **Day 7**: Review. Answer every JS question in Part 14.2 from memory.

### Week 4 — Async JavaScript & ES6+ (Part 4.7-4.10)
- **Day 1**: Read Part 4.7's event loop section slowly. Trace through 3 different
  `setTimeout`/`Promise.then` ordering examples by hand before running them.
- **Day 2**: Build a small app that fetches data with `fetch`, using `async/await` and proper
  `try/catch`, including checking `res.ok` explicitly.
- **Day 3**: Practice `Promise.all` vs sequential `await` — write both versions of a
  multi-request loader and time the difference with `console.time`.
- **Day 4**: Read Part 4.8 (ES6+ features). Refactor an older piece of code you've written to
  use destructuring, spread, optional chaining, and nullish coalescing throughout.
- **Day 5**: Read Part 4.9 (error handling, memory, debounce/throttle). Implement `debounce`
  and `throttle` from scratch, cold, then compare against Part 14.8 Challenges 1-2.
- **Day 6**: Read Part 4.10 (design patterns). Identify which pattern (observer, factory,
  singleton, strategy) best fits three different real problems you've encountered.
- **Day 7**: Review Weeks 3-4. Attempt Part 14.8 Challenges 3, 5, 7-12 cold, one per day
  spread across the rest of this week if needed, checking solutions only after a genuine
  attempt.

### Week 5 — TypeScript & the DOM/Browser APIs (Part 5, Part 6)
- **Day 1**: Read Part 5.1-5.3 (basic types, interfaces vs types, generics). Convert one of
  your earlier JS mini-projects to TypeScript.
- **Day 2**: Read Part 5.4-5.6 (utility types, advanced types, enums). Use `Partial`, `Omit`,
  and `Pick` in a real function signature in your converted project.
- **Day 3**: Read Part 5.7-5.9 (type guards, React+TS, tsconfig). Enable `strict: true` on
  your project and fix every resulting type error.
- **Day 4**: Read Part 6.1-6.3 (DOM manipulation, events, fetch). Build a small vanilla-JS
  component (a tab switcher or accordion) using only `querySelector`/`addEventListener` and
  event delegation — no framework.
- **Day 5**: Read Part 6.4-6.5 (storage, rendering pipeline). Deliberately write a layout-
  thrashing loop, observe it in the Performance tab, then fix it using the batch-read-then-
  write pattern.
- **Day 6**: Read Part 6.6-6.8 (Observers, rAF, Web Workers). Implement a simple scroll-
  triggered fade-in using `IntersectionObserver`, without any animation library.
- **Day 7**: Review Part 14.3 (TypeScript Q&A) and re-read anything from Part 6 that still
  feels shaky.

### Week 6 — React Core (Part 7.1-7.6)
- **Day 1**: Read Part 7.1-7.3 (JSX, components, `useState`). Build a small counter app,
  paying close attention to the functional-update gotcha from Part 7.3.
- **Day 2**: Read Part 7.4 (`useEffect`). Build a component that fetches data on mount with
  proper cleanup (`AbortController`) and correct dependency array usage.
- **Day 3**: Read Part 7.5 (the rest of the core hooks). Use `useRef`, `useContext`, and
  `useReducer` each in a small standalone example.
- **Day 4**: Practice `useMemo`/`useCallback` — deliberately create a performance problem
  (an expensive computation re-running every render) and then fix it, confirming the fix with
  `console.log` call counts.
- **Day 5**: Read Part 7.6 (custom hooks). Extract at least two custom hooks
  (`useLocalStorage`, `useDebounce`) from your own code.
- **Day 6**: Build a small multi-component app (a to-do list with add/remove/toggle/filter)
  using everything from this week.
- **Day 7**: Review. Answer every React hooks-related question in Part 14.4 from memory.

### Week 7 — React Performance, Patterns & Ecosystem (Part 7.7-7.14)
- **Day 1**: Read Part 7.7 (rendering/performance). Deliberately break `React.memo` with a
  non-memoized inline function prop, observe unnecessary re-renders in React DevTools
  Profiler, then fix it.
- **Day 2**: Read Part 7.8-7.9 (Context, forms). Build a small theming system with Context,
  remembering to memoize the provided value.
- **Day 3**: Read Part 7.10-7.11 (error boundaries, React Router). Add a route-based app
  shell with at least 3 routes and one error boundary around a route that can fail.
- **Day 4**: Read Part 7.12 (SSR/Next.js concepts) for conceptual understanding, even without
  building a full Next.js app yet.
- **Day 5**: Read Part 7.13-7.14 (RTL preview, state management). Set up a small Zustand or
  Redux Toolkit store for your to-do app from Week 6.
- **Day 6**: Integrate TanStack Query (or SWR) into a data-fetching component, replacing a
  manual `useEffect` fetch, and compare the code difference.
- **Day 7**: Review Week 6-7. Re-answer all of Part 14.4 from memory, timing yourself.

### Week 8 — Animation Deep Dive: CSS, GSAP, Framer Motion (Part 8)
- **Day 1**: Re-read Part 3.6/6.5 on the rendering pipeline if it's not fully automatic yet,
  then read Part 8.1-8.2.
- **Day 2**: Read Part 8.3-8.4 (GSAP tweens, timelines). Build a hero-section entrance
  sequence using only the position parameter — no `setTimeout` anywhere.
- **Day 3**: Read Part 8.5 (easing/stagger). Animate a grid of cards in with `stagger.from:
  'center'` and compare the feel against a plain left-to-right stagger.
- **Day 4**: Read Part 8.6 (ScrollTrigger). Build a pinned scroll section with a scrubbed
  timeline, using `markers: true` throughout development.
- **Day 5**: Read Part 8.7 (GSAP+React). Integrate GSAP into a React component using
  `useGSAP`, and deliberately trigger React 18 Strict Mode's double-mount to confirm cleanup
  works correctly.
- **Day 6**: Read Part 8.8-8.10 (Framer Motion, SVG animation, FLIP). Build one small
  `AnimatePresence` exit-animation example, and one SVG line-draw effect.
- **Day 7**: Read Part 8.11 (performance/tinkering tips). Profile every animation you built
  this week in DevTools and confirm none of them trigger layout/paint blocks.

### Week 9 — Tooling, Testing, Performance, Accessibility, System Design (Parts 9-13)
- **Day 1**: Read Part 9 (build tools). Inspect your own project's bundle with
  `webpack-bundle-analyzer` or `source-map-explorer` and identify the largest dependency.
- **Day 2**: Read Part 10 (testing). Write unit tests for one pure function, component tests
  with RTL for one component, and (if time allows) one Playwright E2E test for a core flow.
- **Day 3**: Read Part 11 (performance/Web Vitals). Run Lighthouse on a real project and fix
  at least one flagged issue (usually an unsized image or render-blocking resource).
- **Day 4**: Read Part 12 (accessibility). Audit a real page with a screen reader (VoiceOver/
  NVDA) and fix at least 2 issues you find.
- **Day 5**: Read Part 13.1-13.3 (system design approach, autocomplete, infinite scroll).
  Practice explaining the autocomplete race-condition fix out loud, unscripted.
- **Day 6**: Read Part 13.4-13.7 (component library, caching, real-time, file upload).
  Sketch (on paper or a whiteboard tool) a component tree + data flow for one of these
  designs, timed at 20 minutes.
- **Day 7**: Full mock system design session — pick one of Part 13's scenarios, and do the
  entire 5-step framework from Part 13.1 out loud, timed at 35-40 minutes, ideally with
  another person listening.

### Week 10 — Full Interview Simulation & Gap-Filling
- **Day 1-2**: Redo every question in Part 14.1-14.4 (HTML/CSS/JS/TS/React) from memory,
  timed, flagging any you hesitate on for extra review.
- **Day 3**: Redo Part 14.5-14.7 (Animation/Browser/System Design recap) the same way.
- **Day 4-5**: Re-implement all 12 of Part 14.8's coding challenges cold, without looking at
  the guide, timing each to under 10 minutes.
- **Day 6**: Do a full mock interview (with a friend, mentor, or a mock-interview platform)
  combining a coding question + a short system design question in one session.
- **Day 7**: Rest, lightly skim Part 15's cheat sheets, and go into interviews confident —
  by this point you've built real things with every technology in this guide, not just read
  about them.

## 15.8 Frequently Asked Questions

**Q: I only have 2 weeks before an interview, not 10 — what should I prioritize?**
A: Skip straight to Part 4 (JavaScript fundamentals) and Part 7 (React) if the role is
React-focused, since these two topics dominate real interview time across nearly every
company. Then do Part 13 (System Design) and Part 14 (the full Q&A bank) as your final week,
since they're the highest-density review material. Come back for Parts 8-12 (Animation,
Tooling, Testing, Performance, Accessibility) afterward if you get the job, or if the specific
role explicitly emphasizes them (e.g., a "creative/motion-focused frontend" role should
prioritize Part 8 much earlier).

**Q: Do I really need to learn TypeScript, or is plain JavaScript enough?**
A: The overwhelming majority of mid-to-senior frontend job postings now list TypeScript as a
requirement or strong preference, and most serious codebases have migrated to it. Learn it —
Part 5 is intentionally compact because TypeScript's core ideas build directly on JavaScript
concepts you already know from Part 4, not because it's less important.

**Q: Should I learn GSAP before or after React?**
A: Learn core JavaScript (Part 4) and the browser rendering pipeline (Part 6.5) first — GSAP
is "just" a very well-designed JavaScript library, and understanding closures/`this`/the
event loop makes GSAP's API make far more sense. You can learn GSAP's basics (Part 8.3-8.6)
in parallel with early React (Part 7), and save the GSAP+React integration section (8.7) for
after you're comfortable with `useEffect` and cleanup functions specifically.

**Q: Is Redux still worth learning in 2026, given Zustand/Context/TanStack Query exist?**
A: Yes, for two reasons: many large, established codebases still use it, so you'll likely
encounter it on the job even if you wouldn't choose it for a new project; and understanding
its action/reducer/selector model deeply informs how you reason about *any* state management
approach, including Zustand's near-identical (simpler) model. Learn Redux Toolkit
specifically — not legacy hand-written Redux with manual action-type constants and switch
statements, which is far more boilerplate than modern usage requires.

**Q: How much math/DSA (LeetCode-style algorithms) do frontend interviews actually need?**
A: Far less than backend/general SWE interviews, but not zero — expect array/string
manipulation problems (often overlapping with Part 14.8's style: implement debounce, flatten
an array, an LRU cache) rather than heavy graph/DP algorithm questions. The emphasis shifts
toward practical JS mastery, React-specific reasoning, and system design over abstract
algorithmic complexity, but basic Big-O fluency is still expected.

**Q: What's the single highest-leverage thing I can do this week if I only have a few hours?**
A: Type out and run the closure-in-a-loop example (Part 4.2) and the microtask-vs-macrotask
ordering example (Part 4.7) until you can explain both from memory, unscripted, to another
person. These two examples alone test scope, closures, hoisting, `this`-adjacent reasoning,
promises, and the event loop — an outsized fraction of real JS interview signal concentrated
into two small code snippets.

**Q: My code works but feels "un-idiomatic" — how do I develop better React instincts?**
A: Read real, well-maintained open-source React codebases (many popular component libraries
and starter templates are on GitHub) and notice patterns: how they structure custom hooks,
where they colocate state, how they handle loading/error states consistently. Pattern-matching
against code written by experienced teams builds instincts faster than tutorials alone.

**Q: Should I memorize the coding challenges in Part 14.8, or truly understand them?**
A: Understand them — interviewers frequently ask a slight variation (add a `leading`/
`trailing` option to debounce, make the EventEmitter support wildcard events, make the LRU
cache thread-safe conceptually) specifically to filter out memorized-but-not-understood
answers. If you can explain *why* each line exists, variations become easy; if you've only
memorized the final code, any twist will expose the gap.

**Q: How important is it to know exactly which CSS property triggers layout vs paint vs
composite?**
A: Genuinely important for senior roles and for animation-heavy roles specifically — it's one
of the most reliable ways interviewers distinguish "has used CSS" from "understands how the
browser actually renders a page," and it directly explains *why* the transform/opacity
animation rule (Part 3.6) exists rather than just asserting it as a rule to memorize.

**Q: What if I get asked about a library/tool not covered in this guide?**
A: Use the "I don't know, but here's how I'd find out" approach from Part 14.9 — then relate
it to the closest concept you *do* know from this guide (e.g., if asked about SolidJS's
fine-grained reactivity and you only know React, compare it to how React's virtual DOM
diffing achieves a similar "only update what changed" goal via a different mechanism). This
demonstrates transferable understanding rather than memorized trivia.

**Q: Do I need to be a design/UX expert too?**
A: No, but basic visual/UX literacy (contrast, spacing consistency, clear affordances for
interactive elements, sensible loading/empty/error states) is expected of any frontend
engineer and comes up in both coding and system design rounds — Part 11 and Part 12
specifically build the technical half of this (performance and accessibility), which
overlaps heavily with good UX in practice.

**Q: How do I practice explaining concepts out loud if I don't have a study partner?**
A: Record yourself explaining a concept (e.g., the event loop, or FLIP) on your phone, then
play it back — you'll immediately notice where your explanation was vague or where you said
"it just... works" instead of actually explaining the mechanism. This single habit closes the
gap between "I understand this" and "I can clearly explain this to someone else," which is
exactly what's being evaluated in an interview.

**Q: Is it normal to still feel nervous even after finishing this entire guide?**
A: Yes — competence and confidence develop on different timelines, and confidence usually
lags behind actual skill by weeks. The fix isn't more reading; it's more *doing* (mock
interviews, building small real projects, explaining concepts out loud) — which this guide's
roadmap (15.7) is deliberately structured around, rather than passive re-reading.

## 15.9 Common Mistakes — 40 Real-World Frontend Bugs to Recognize Instantly

**1. Forgetting `e.preventDefault()` on a form submit handler.**
Symptom: the page fully reloads/navigates on submit, losing all app state and any in-flight
JS. Why: a `<form>`'s default browser behavior is a full navigation POST/GET unless
explicitly prevented. Fix: always call `event.preventDefault()` as the very first line of a
JS-driven submit handler (Part 2.4).

**2. Using array index as `key` in a reorderable/filterable list.**
Symptom: after reordering or filtering, an input's typed value or a CSS transition appears
attached to the wrong row. Why: React matches elements across renders by `key`, and index
no longer reliably identifies "the same logical item" once order changes. Fix: use a stable
unique ID from the underlying data (Part 7.7).

**3. Mutating state directly instead of creating a new reference.**
Symptom: calling `setState` after `array.push(x)` or `obj.field = y` does nothing visible.
Why: React (and most state libraries) detect changes via reference comparison; mutating in
place leaves the reference identical. Fix: `setState([...array, x])` or
`setState({...obj, field: y})` (Part 7.3).

**4. Missing `useEffect` cleanup for subscriptions, timers, or event listeners.**
Symptom: "Can't perform a React state update on an unmounted component" warnings, or genuine
memory leaks in long-lived SPA sessions. Why: the subscription/timer/listener keeps running
and referencing component state after the component has unmounted. Fix: always return a
cleanup function from `useEffect` that reverses whatever the effect set up (Part 7.4, 4.9).

**5. Not checking `res.ok` after `fetch()`.**
Symptom: error responses (404/500) are silently treated as success, and `.json()` parsing
fails downstream with a confusing error, or the app renders an error payload as if it were
valid data. Why: `fetch()` only rejects on network-level failures, not HTTP error statuses.
Fix: explicitly check `if (!res.ok) throw new Error(...)` (Part 6.3).

**6. Comparing objects/arrays with `===` expecting a "content equality" check.**
Symptom: `if (newArr === oldArr)` is always `false` even when contents are identical. Why:
`===` on non-primitives compares references, not contents. Fix: use a deep-equality utility,
or (better in React) restructure so you're comparing primitive derived values instead.

**7. `0 == ''` and other loose-equality surprises reaching production code.**
Symptom: a validation check like `if (value == '')` unexpectedly passes for `value = 0`. Why:
`==` coerces types before comparing. Fix: use `===` and be explicit about which falsy values
you actually want to treat as "empty" (Part 4.1).

**8. Forgetting `await` inside an `async` function, silently working with a Promise object
instead of the resolved value.**
Symptom: logging `[object Promise]` instead of the expected data, or a downstream `.map()`
call throwing because you're calling it on a Promise, not an array. Fix: always `await` a
call that returns a Promise before using its result.

**9. Using `forEach` with an `async` callback expecting it to wait.**
Symptom: code after the loop runs before any of the async work inside the loop finishes. Why:
`forEach` does not await its callback's returned promise. Fix: use a `for...of` loop with
`await`, or `Promise.all(arr.map(...))` for parallel execution (Part 4.7).

**10. Leaving `console.log`/debugger statements in production code.**
Symptom: sensitive data or noisy debug output visible in the browser console to any end user.
Why: forgotten during development. Fix: lint rules (`no-console`) enforced in CI, and a final
pre-merge search sweep.

**11. Not handling the loading/error/empty states of a data-fetching component.**
Symptom: a blank screen or a crash while data is loading, or a confusing empty white area
when a list genuinely has zero items. Fix: always explicitly render distinct UI for loading,
error, empty, and success states — never assume the "happy path" is the only path.

**12. Applying `will-change` permanently to many elements.**
Symptom: the page feels sluggish or the browser tab's memory usage balloons. Why: every
promoted compositor layer consumes GPU memory continuously. Fix: apply `will-change` briefly,
just before an animation starts, and remove it once finished (Part 3.6, 8.11).

**13. Animating `width`/`height`/`top`/`left` instead of `transform` for movement/resizing.**
Symptom: animations feel janky, especially on lower-end devices, and DevTools' Performance
tab shows purple Layout blocks during the animation. Fix: prefer `transform: translate()`/
`scale()` wherever visually equivalent (Part 3.6, 6.5).

**14. Removing focus outlines globally (`*:focus { outline: none; }`).**
Symptom: keyboard users can no longer see which element is focused anywhere on the site — a
serious accessibility regression. Fix: use `:focus-visible` to hide the ring only for
pointer-driven focus, never remove it universally (Part 12.3).

**15. Storing auth tokens in `localStorage`.**
Symptom: a successful XSS attack can trivially exfiltrate the token, since any JS on the page
can read `localStorage`. Fix: prefer `httpOnly` cookies for session/auth tokens, inaccessible
to JavaScript entirely (Part 6.4).

**16. Rendering untrusted user content with `innerHTML` without sanitization.**
Symptom: a stored XSS vulnerability — a malicious `<script>`/`onerror` payload from one user
executes in another user's browser. Fix: use `textContent` for plain text, or a vetted
sanitizer library (DOMPurify) if genuine HTML rendering is required (Part 6.1).

**17. Not memoizing a Context Provider's `value` object.**
Symptom: every consumer of the context re-renders on every render of the Provider, even when
the logical value hasn't changed. Why: `{ user, login }` is a brand-new object reference every
render unless memoized. Fix: wrap it in `useMemo` (Part 7.8).

**18. Reflexively wrapping every value/function in `useMemo`/`useCallback`.**
Symptom: code becomes harder to read with no measurable performance benefit, sometimes
slightly *slower* due to memoization overhead. Fix: only memoize genuinely expensive
computations, or values/functions passed to a `React.memo`-wrapped child (Part 7.5, 7.7).

**19. Using offset-based pagination (`?page=3`) for a frequently-changing feed.**
Symptom: users see duplicated or skipped items when scrolling, because items were
inserted/removed between page loads. Fix: use cursor-based pagination anchored to a specific
item ID/timestamp (Part 13.3).

**20. Building a custom `<div onClick>` "button" without keyboard support.**
Symptom: keyboard-only and screen-reader users cannot activate the control at all. Fix: use a
real `<button>` whenever possible; if truly custom, add `tabindex="0"`, `role="button"`, and
manual `Enter`/`Space` key handling (Part 2.8, 12.4).

**21. Not debouncing a search-as-you-type input.**
Symptom: a network request fires on every single keystroke, overwhelming the backend and
often producing out-of-order responses. Fix: debounce the input (~250-300ms), and guard
against race conditions with an `AbortController` (Part 4.9, 13.2).

**22. Forgetting `gsap.registerPlugin(ScrollTrigger)` before using ScrollTrigger.**
Symptom: ScrollTrigger silently no-ops — no errors, the animation just never triggers. Fix:
always register plugins once at app startup before using them (Part 8.6).

**23. Not cleaning up GSAP animations in React, especially under Strict Mode.**
Symptom: animations double up, ScrollTriggers duplicate, or animations appear "broken" only
in development (where Strict Mode intentionally double-mounts components). Fix: use
`useGSAP` or `gsap.context()` + `ctx.revert()` in cleanup (Part 8.7).

**24. Using `gsap.from()` when the element's current styles are already in an inconsistent
state.**
Symptom: an animation's starting point looks wrong or inconsistent depending on what happened
before it ran. Fix: use `gsap.fromTo()` for fully explicit, reproducible start/end states
(Part 8.3).

**25. Not respecting `prefers-reduced-motion`.**
Symptom: users with vestibular disorders experience real discomfort from unnecessary motion
on your site. Fix: check the media query in both CSS and JS/GSAP and drastically reduce or
disable non-essential animation when it's set (Part 8.11).

**26. Importing an entire large library for one small utility function.**
Symptom: bundle size balloons far more than expected for a small feature. Why: `import _ from
'lodash'` pulls in the whole library even if you only use `debounce`. Fix: import the specific
submodule (`lodash/debounce`) or use a tree-shakeable alternative (Part 11.3).

**27. Not setting `width`/`height` (or `aspect-ratio`) on images, causing layout shift.**
Symptom: content visibly jumps down as images load in, hurting CLS and general perceived
quality. Fix: always reserve the image's space up front (Part 2.5, 11.1).

**28. Testing implementation details instead of user-visible behavior.**
Symptom: tests break on harmless refactors (renaming a state variable, changing a class to a
hook) even though the actual user-facing behavior is unchanged. Fix: query by role/label/text
(RTL's philosophy) rather than internal state or CSS class names (Part 10.3).

**29. Using `getByTestId` as the default query in React Testing Library.**
Symptom: tests pass even when a real accessibility issue exists (e.g., a button with no
accessible name), because `data-testid` bypasses the accessibility tree entirely. Fix:
default to `getByRole`, reserving `getByTestId` as a last resort (Part 10.3).

**30. Not using a lockfile, or not committing it.**
Symptom: "works on my machine" bugs where a teammate/CI gets a different transitively-resolved
dependency version than you did. Fix: always commit `package-lock.json`/`yarn.lock`/
`pnpm-lock.yaml`, and use `npm ci` (not `npm install`) in CI (Part 9.1).

**31. Skipping the `alt` attribute, or using a non-empty `alt` on purely decorative images.**
Symptom: screen reader users hear irrelevant filler ("image1234.jpg") for decorative images,
or hear nothing useful for meaningful ones. Fix: meaningful images get a real description;
purely decorative images get `alt=""` explicitly (Part 2.5, 12.5).

**32. Building a modal/dialog without a focus trap.**
Symptom: `Tab` key navigation "escapes" the open modal into the page content behind it,
disorienting keyboard/screen-reader users. Fix: implement (or use a library that implements)
proper focus trapping — focus should cycle only within the open dialog until it's dismissed
(Part 12.4, 13.4).

**33. Not virtualizing a very long list.**
Symptom: scrolling becomes visibly janky, and the page becomes slow to interact with, once a
list grows into the thousands of rendered DOM nodes. Fix: use list virtualization
(react-window/TanStack Virtual) to render only the visible subset (Part 7.7, 13.3).

**34. Treating fetched server data exactly like local client state (manual loading/error
flags, no caching).**
Symptom: redundant network requests for the same data across different components, and a lot
of repetitive boilerplate for loading/error/caching logic. Fix: use a dedicated server-state
library like TanStack Query/SWR instead of reimplementing caching manually with
`useState`/Redux (Part 7.14, 13.5).

**35. Choosing WebSockets when a simpler one-directional stream (SSE) would suffice.**
Symptom: unnecessary infrastructure complexity (connection state management, reconnection
logic, a pub-sub backplane for scaling across server instances) for a feature that never
actually needed bidirectional communication. Fix: clarify whether the client genuinely needs
to send messages back over the same channel before reaching for WebSockets (Part 13.6).

**36. Writing a `tsconfig.json` without `"strict": true`.**
Symptom: `null`/`undefined` silently assignable everywhere, `any` types spreading unchecked,
losing most of TypeScript's actual bug-catching value while still paying its tooling
overhead. Fix: always enable `strict` mode on new TypeScript projects (Part 5.9).

**37. Using `any` as a "quick fix" for a type error instead of a real fix.**
Symptom: type safety silently disappears at that point and "infects" anything that value
touches downstream, defeating the purpose of using TypeScript at all. Fix: use `unknown` and
properly narrow it, or take the extra few minutes to model the real type correctly (Part 5.1).

**38. Not providing a fallback UI for `React.lazy`/`Suspense`.**
Symptom: a blank flash or a confusing frozen UI while a lazily-loaded chunk downloads. Fix:
always wrap lazy components in `<Suspense fallback={<Spinner />}>` (Part 7.7).

**39. Forgetting that `Promise.all` rejects immediately on the first failure, discarding the
other results.**
Symptom: a batch operation where 9 out of 10 requests actually succeeded reports total failure
with no access to the 9 successful results. Fix: use `Promise.allSettled` when you need to
know the outcome of every promise regardless of individual failures (Part 4.7, 14.2 Q8).

**40. Assuming `NaN === NaN` or using `indexOf` to search for `NaN` in an array.**
Symptom: `[NaN].indexOf(NaN)` returns `-1` even though `NaN` is clearly in the array, because
`indexOf` uses `===` internally, and `NaN` is never `===` to itself. Fix: use
`.includes(NaN)` (which uses the SameValueZero algorithm and correctly finds it), or
`Number.isNaN()` for a direct check (Part 4.1, 14.2 Q10).

## 15.10 Worked Debugging Scenarios

Real interview "debug this" rounds (and real production incidents) tend to look like these.
Practice the *investigation process*, not just memorizing the specific root cause.

### Scenario 1: "The button click handler fires twice"

**Symptom**: clicking a button triggers its `onClick` handler two times instead of one, but
only in production, not in local development.

**Investigation**: check if the event listener is attached more than once — e.g., inside a
`useEffect` with a missing/incorrect dependency array that re-runs the effect (and re-attaches
a `document.addEventListener` call) without cleaning up the previous listener first. In
development, React 18 Strict Mode's double-invoke of effects is often incorrectly blamed —
but if the bug also reproduces in production (where Strict Mode's double-invoke doesn't apply
the same way), the real cause is almost always a genuinely missing cleanup function.

**Root cause**: a `useEffect(() => { document.addEventListener('click', handler); }, [])`
with **no return cleanup function** — if this component ever mounts more than once during the
session (route re-entry, a parent remounting due to a changed `key`), each mount adds another
listener that's never removed.

**Fix**: always return `() => document.removeEventListener('click', handler)` from the effect
(Part 7.4, mistake #4 in 15.9).

### Scenario 2: "The list re-renders every single item on every keystroke in an unrelated
search box"

**Symptom**: typing in a search input causes visible lag, and React DevTools Profiler shows
every row of an unrelated 500-item list re-rendering on each keystroke.

**Investigation**: check what state the search input's `onChange` actually updates, and trace
which components read that state — likely the search state lives in a common parent above
both the search box and the list, causing the parent (and therefore, by default, every child
including the list) to re-render on every keystroke.

**Root cause**: the list's rows aren't wrapped in `React.memo`, or they are but receive a
non-memoized inline callback prop (e.g., `onClick={() => handleSelect(item.id)}`) that's a new
function reference every render, defeating `React.memo`'s shallow comparison.

**Fix**: wrap list row components in `React.memo`, and memoize any callback props passed to
them with `useCallback` (Part 7.7, mistake #18's inverse — this time memoization is actually
warranted because profiling proved a real cost).

### Scenario 3: "Data from a fast-typed search sometimes shows results for an earlier,
already-abandoned query"

**Symptom**: typing quickly, results occasionally flicker to show what looks like results for
a previous, shorter search term before "correcting" to the right ones a moment later.

**Investigation**: this is the classic autocomplete race condition (Part 13.2) — log each
request's query string and completion order; you'll see that a slower request for an earlier
(shorter) query term completes *after* a faster request for the current (longer) query term.

**Root cause**: no cancellation or sequencing mechanism — every keystroke's request is treated
as independent, and whichever happens to resolve last wins, regardless of which was actually
requested last.

**Fix**: use an `AbortController` per request, aborting the previous one whenever a new request
starts, or tag requests with an incrementing sequence number and ignore any response that
isn't the latest (Part 13.2).

### Scenario 4: "The page's Cumulative Layout Shift score is bad, but nothing looks obviously
broken visually"

**Symptom**: Lighthouse reports a high CLS score, but casually looking at the page doesn't
reveal an obvious jump.

**Investigation**: use Lighthouse's/DevTools' layout shift visualization (or the Performance
tab's "Experience" section) to see exactly which elements shifted and when — commonly, an ad
slot, an embedded widget, or a web font swap (`font-display: swap`) causes a subtle but
measurable shift that's easy to miss with the naked eye but still hurts the metric.

**Root cause**: images or embeds without explicit `width`/`height`/`aspect-ratio` reserved
space, or a web font whose fallback metrics don't closely match the real font, causing text
to reflow slightly when the real font loads.

**Fix**: reserve space for all images/embeds up front; use `size-adjust`/closely-matched
fallback fonts, or `font-display: optional` if a layout shift on font-swap is unacceptable for
that specific text (Part 2.5, 11.1).

### Scenario 5: "A GSAP ScrollTrigger animation works on the first page load but breaks after
navigating away and back in a single-page app"

**Symptom**: a scroll-triggered section animates correctly the first time, but on a second
visit (via client-side routing, not a full page reload) the trigger positions seem wrong or
the animation doesn't fire at all.

**Investigation**: check whether the previous mount's ScrollTrigger instance was ever properly
killed — log `ScrollTrigger.getAll().length` before and after navigating away and back; a
growing count confirms leaked, stacked-up instances from previous mounts.

**Root cause**: missing `gsap.context()`/`useGSAP` cleanup (Part 8.7, mistake #23 in 15.9) —
each mount creates new ScrollTrigger instances pointing at DOM elements that may have already
been removed/replaced, without ever cleaning up the old ones.

**Fix**: use `useGSAP` with a proper `scope`, or manually call `ctx.revert()` in the
`useEffect` cleanup function, every single time.

### Scenario 6: "Fetch calls silently fail with no error, no data, and no console output"

**Symptom**: a `fetch` call to an external API appears to just... do nothing, with no
network error, no thrown exception, and the `.then()` callback never seems to fire.

**Investigation**: open the Network tab and check whether the request even leaves the
browser, and check the Console for a `CORS` error message specifically — this failure mode
is easy to miss because the *browser* blocks the *response* from being handed back to your
JS after the request already completed on the wire, which can look like "nothing happened"
rather than an obvious network failure.

**Root cause**: the target server doesn't include the correct `Access-Control-Allow-Origin`
header for your origin, and the browser's CORS policy silently withholds the response body
from your JavaScript as a security measure (Part 6.3, glossary "CORS").

**Fix**: this must be fixed server-side (correct CORS headers) or by routing the request
through your own backend/a proxy that's allowed to talk to the external API directly.

### Scenario 7: "A `useEffect` runs infinitely, pegging the CPU"

**Symptom**: the browser tab becomes unresponsive; React DevTools Profiler (or just a
`console.log` inside the effect) shows the same `useEffect` firing continuously, hundreds of
times per second.

**Investigation**: inspect the effect's dependency array — check if any listed dependency is
recreated as a new reference on every render (a new object/array/function literal), which
`Object.is` always considers "changed," causing the effect to re-run every render, which (if
the effect itself triggers a state update) causes another render, forming an infinite loop.

**Root cause**: something like `useEffect(() => { setData({ ...data, x: 1 }); }, [{ ...data
}])` (an inline object literal in the dependency array) or an effect that unconditionally
calls `setState` with a value that's always considered "different" from the previous state.

**Fix**: ensure dependency array entries are stable primitives or properly memoized
references, and ensure any `setState` call inside an effect has a real, changing condition
gating it, not an unconditional call on every effect run (Part 7.4).

### Scenario 8: "TypeScript compiles fine but the app crashes at runtime with 'x is not a
function'"

**Symptom**: no TypeScript compiler errors, but a runtime `TypeError: x.someMethod is not a
function`.

**Investigation**: check whether `any` appears anywhere along the path that produced `x` —
search for `as any`, an untyped third-party import, or a `// @ts-ignore` comment near the
code that constructs or receives `x`.

**Root cause**: an `any`-typed value (often from `JSON.parse()`'s return type, or a poorly-
typed external library) silently disabled type checking for that entire branch of code,
letting an incorrect assumption about `x`'s shape slip through undetected until runtime
(Part 5.1, mistake #37 in 15.9).

**Fix**: replace the `any` with `unknown` plus proper narrowing/validation (a runtime schema
validator like Zod is the robust answer for genuinely external/untyped data), so the type
system can actually catch this class of bug at compile time going forward.

### Scenario 9: "The exact same component looks different in Chrome vs Safari"

**Symptom**: visual inconsistency in spacing, font rendering, or flex behavior between
browsers, despite identical CSS.

**Investigation**: check for CSS features with differing default behaviors or partial support
across engines — a very common concrete cause is `gap` inside flexbox (supported broadly now,
but historically inconsistent), default `<button>`/form control styling differences, or a
CSS feature genuinely only supported in one engine (check caniuse.com-style compatibility
data before relying on cutting-edge CSS without a fallback).

**Root cause**: browser-default user-agent stylesheet differences (each browser ships
different defaults for form controls, margins, font rendering) that weren't fully normalized
by a CSS reset/normalize stylesheet.

**Fix**: use a CSS reset/normalize stylesheet as a baseline, and explicitly test in every
target browser rather than assuming visual parity from identical authored CSS.

### Scenario 10: "The app works locally but the production build shows a blank white screen"

**Symptom**: `npm run dev` works perfectly; the production build (`npm run build` + serving
the static output) shows a completely blank page with a console error referencing a missing
module or an unexpected token.

**Investigation**: check the browser console for the specific error first — a common concrete
cause is an environment-variable-dependent code path that behaves differently in production
mode (e.g., code gated behind `process.env.NODE_ENV !== 'production'` that silently vanishes
from the production bundle), or a dynamic `import()` path that isn't correctly resolved by the
production bundler's asset base path configuration.

**Root cause**: frequently a base-path/public-path misconfiguration (the production build
assumes assets are served from `/`, but they're actually deployed under a subpath), or a
top-level uncaught exception during the app's initial render with no error boundary to catch
and surface it gracefully (compounding the "blank screen" mystery, since the actual error may
have been logged but the page gives no visual indication anything went wrong).

**Fix**: check the deployed base path configuration in the bundler config, and always wrap
your app's root in a top-level error boundary (Part 7.10) so a genuine rendering crash at
least shows a visible error message instead of a silent blank screen.

## 15.11 Recommended Resources by Topic

Use this list as a next-step reference once you finish this guide — official documentation
should always be your primary source of truth, since libraries/frameworks evolve continuously.

**HTML & CSS**: MDN Web Docs (the single best reference for every HTML element, CSS property,
and browser API — bookmark it and search it constantly rather than guessing syntax). The
`web.dev` learning paths (Google's own frontend education site) cover CSS layout and
performance particularly well, with interactive examples. For deep CSS layout mastery
specifically, the free "Flexbox Froggy" and "Grid Garden" browser games are genuinely useful,
short, hands-on drills for internalizing Flexbox/Grid syntax through play rather than reading.

**JavaScript**: "You Don't Know JS" (book series, freely readable on GitHub) remains one of
the most thorough treatments of closures, `this`, prototypes, and async — exactly the topics
Part 4 of this guide covers, at even greater depth if you want to go further. MDN's
JavaScript guide and reference are, again, the canonical source for exact API behavior.
javascript.info is a well-organized, modern, example-heavy alternative reference that pairs
well with hands-on practice.

**TypeScript**: The official TypeScript Handbook (typescriptlang.org) is genuinely excellent
and far more approachable than most people expect — read it directly rather than relying
solely on third-party tutorials, since it's kept in sync with the actual compiler behavior.

**React**: The official React documentation (react.dev) was substantially rewritten in
recent years specifically around hooks and modern patterns, and is the most reliable, most
up-to-date source — many older blog posts/tutorials predate hooks or reflect deprecated
patterns (class components, legacy Context API, `componentWillMount`), so always
cross-reference against the current official docs.

**Animation & GSAP**: GreenSock's own documentation and their "GSAP 3 Express" free video
course are the best starting points, since GSAP's API surface is large and their own
maintainers write the clearest explanations of edge cases (especially around ScrollTrigger's
`start`/`end` syntax). The Framer Motion documentation is similarly authoritative for its own
API, with a strong focus on runnable interactive examples.

**Build tools & performance**: The Vite documentation is concise and genuinely readable
end-to-end in an afternoon. `web.dev`'s Core Web Vitals section is the canonical reference for
performance metric definitions and remediation guidance, maintained directly by the Chrome
team that defines these metrics.

**Accessibility**: The W3C's WAI-ARIA Authoring Practices Guide (APG) provides concrete,
tested reference implementations (with full keyboard interaction patterns) for every common
composite widget (tabs, comboboxes, dialogs, menus) — invaluable when building a custom
component that needs to match established accessibility conventions exactly.

**System design & interviews**: Practicing by writing out full answers to Part 13's scenarios
from scratch, then comparing your answer against the given tradeoffs, is more valuable than
passively reading additional system design content — the skill being tested is structured
live reasoning, which only improves with repeated practice under time pressure, ideally with
another person listening and asking follow-up questions.

## 15.12 Interview Format Notes by Company Type

**Large tech companies (FAANG-style, big tech)**: Typically 4-6 rounds across multiple days:
a recruiter screen, one or two coding rounds (often generic algorithmic problems alongside
frontend-specific ones, sometimes on a shared collaborative editor without full IDE
autocomplete), a system design round (frequently frontend-specific, matching Part 13's
style), and a behavioral/values round. Expect a strong emphasis on communicating your thought
process clearly, since these companies interview at high volume and rely heavily on
structured, comparable rubrics across candidates. Take-home assignments are less common at
this tier; most evaluation happens live.

**Mid-size product companies**: Often 3-4 rounds, frequently including a practical
"build a small feature" live-coding round using their actual tech stack (e.g., "add a
new field to this form and wire it to the API") rather than abstract algorithm puzzles —
signaling that day-to-day productivity in their specific codebase matters as much as
raw algorithmic ability. Expect deeper, more specific questions about the frameworks/
libraries they actually use in production (if they use GSAP heavily for marketing pages,
expect real ScrollTrigger questions; if they're deep in Next.js, expect real SSR/hydration
questions).

**Startups**: Highly variable, but commonly a single longer technical conversation/pairing
session (60-90 minutes) covering both breadth (a few rapid-fire concept questions) and depth
(a real, small coding exercise, sometimes literally a scaled-down version of a real feature
they need built). Take-home projects are more common at this tier, given smaller hiring
teams with less bandwidth for many live rounds — expect a project brief with a tight scope
and a follow-up conversation walking through your specific decisions and tradeoffs.

**Agencies/consultancies**: Often emphasize breadth across many frameworks/CMS platforms
(since client work varies widely) over extreme depth in any single one, alongside genuine
design/UX sensibility and client-communication skills, since agency frontend engineers often
interact directly with client stakeholders, not just internal product teams.

**Across all company types**: The single most common mistake candidates make is treating
every round identically regardless of format — a live pairing session rewards fast, clear
communication and pragmatic tradeoffs; a formal system design round rewards structured,
comprehensive coverage of the 5-step framework (Part 13.1); a take-home rewards genuinely
clean, well-tested, well-documented code more than raw cleverness, since there's no live
observer to explain your reasoning to. Adapt your approach to the specific format rather than
running the same playbook everywhere.

## 15.13 Extended Glossary — Round 2 (30 More Terms)

**Accessible name**: The text a screen reader announces for an interactive element, computed
from (in priority order roughly) `aria-labelledby`, `aria-label`, associated `<label>` text,
`alt` text, or visible text content — often different from what's visually displayed.

**Atomic CSS**: The architectural principle behind utility-first frameworks like Tailwind,
where each class does exactly one small thing (e.g., `.mt-4` sets margin-top only), composed
together in markup rather than combined into custom semantic class names.

**Behavioral round**: An interview stage focused on past experiences and soft skills (conflict
resolution, ownership, communication) rather than technical execution, commonly assessed via
the STAR method (Part 14.9).

**Bundle splitting**: See "code splitting" — breaking a JS bundle into multiple
separately-loadable chunks instead of one monolithic file.

**Cache invalidation**: The process of marking cached data as stale/outdated so it gets
refetched, typically triggered after a mutation that's known to have changed the underlying
data (Part 13.5).

**Compound component pattern**: A React API design style where a parent component and its
children work together implicitly (often via Context) to form one cohesive unit, e.g.
`<Tabs><Tabs.List><Tabs.Tab/></Tabs.List><Tabs.Panels/></Tabs>` (Part 13.4).

**Content Security Policy (CSP)**: An HTTP response header that restricts which sources of
scripts, styles, and other resources a page is allowed to load from, providing defense-in-
depth against XSS even if a sanitization bug slips through elsewhere.

**Critical rendering path**: The sequence of steps (HTML/CSS parsing, render tree
construction, layout, paint) the browser must complete before the first pixels appear on
screen — optimizing this path is the core goal of most loading-performance work (Part 1.2,
11.1).

**Dead code elimination**: A broader term encompassing tree-shaking, referring to any
compiler/bundler technique that removes code proven to be unreachable or unused.

**Design token**: A named, reusable value (a color, spacing unit, font size) representing a
single design decision, typically implemented as a CSS custom property in a design system
(Part 3.9, 13.4).

**Feature flag**: A runtime toggle that enables/disables a piece of functionality without a
new deployment, commonly used for gradual rollouts, A/B testing, and safely shipping
incomplete features behind a flag until ready.

**First Contentful Paint (FCP)**: The time until the browser renders the first piece of DOM
content (text, image, canvas) — an earlier, less holistic metric than LCP, but still a useful
signal of perceived loading speed.

**Idle callback**: Work scheduled via `requestIdleCallback` to run only when the browser has
genuinely spare time during a frame, useful for low-priority background work that shouldn't
compete with rendering/interaction responsiveness.

**Immutability**: The practice of never mutating existing data structures in place, always
producing new ones instead — foundational to how React (and Redux) detect state changes
cheaply via reference comparison rather than deep value comparison (Part 7.3).

**Instrumentation**: Code added specifically to measure/observe application behavior in
production (performance timings, error tracking, analytics events), as distinct from the
application's core business logic.

**Just-In-Time (JIT) compilation (in the context of Tailwind)**: Generating only the specific
utility CSS classes actually used in your markup, on demand, instead of shipping a
pre-generated stylesheet containing every possible utility class combination — dramatically
smaller final CSS output.

**Keyboard trap**: An accessibility bug where keyboard focus gets stuck inside (or unable to
enter) a particular region of the page, preventing full keyboard navigation — the opposite,
unintentional failure mode of a properly-implemented focus trap in a modal (Part 12.3, 15.9
mistake #32).

**Lighthouse score**: An automated, 0-100 composite score across performance, accessibility,
best practices, and SEO categories, generated by running a page through Google's Lighthouse
auditing tool (Part 11.2).

**Middleware (in state management)**: A function that intercepts dispatched actions before
they reach a reducer, commonly used for logging, async side-effect handling (e.g.
redux-thunk/redux-saga), or persisting state to storage.

**Module bundler**: See "bundler" — the specific term commonly used for Webpack-style tools
that combine many JS modules into fewer output files.

**Optimistic concurrency**: Assuming conflicts between concurrent updates are rare and
handling them only if they actually occur (e.g., via a version number check on write),
contrasted with pessimistic locking, which prevents concurrent access upfront.

**Polyfill**: Code that implements a modern JavaScript/Web API feature for older browsers/
environments that don't natively support it, allowing you to safely use the modern API in
your source code regardless of runtime support.

**Progressive enhancement**: A design philosophy of building a fully functional baseline
experience first (working HTML forms, semantic structure), then layering richer JS-driven
interactivity on top — as opposed to requiring JS just for basic functionality to work at all.

**Rehydration**: See "hydration" — sometimes used specifically to describe re-attaching
interactivity after a subsequent SSR page navigation, rather than only the very first page
load.

**Render props**: An older React pattern (largely superseded by hooks) for sharing logic
between components by passing a function as a prop that returns JSX, e.g.
`<DataProvider render={data => <Display data={data} />} />`.

**Selector (state management)**: A function that extracts and returns a specific slice of
state from a larger store, forming the basis of granular, non-cascading re-render
subscriptions in Redux/Zustand (Part 7.14).

**Shadow DOM**: A browser feature providing true style/markup encapsulation for a Web
Component's internal implementation, preventing its internal styles from leaking out (or
external page styles from leaking in) unless explicitly designed to (Part 2.7).

**Source map**: A file mapping minified/transpiled production code back to its original
source, enabling readable stack traces and debugging in DevTools even though the browser is
actually running a heavily transformed bundle.

**Suspense boundary**: A `<Suspense>` component in React that shows a fallback UI while its
descendants are not yet ready to render (data still loading, or a lazy-loaded chunk still
downloading) (Part 7.7).

**Time to Interactive (TTI)**: A (largely superseded, but still occasionally referenced)
performance metric measuring when a page becomes reliably interactive — largely replaced in
modern practice by INP as the primary responsiveness metric (Part 11.1).

**Web App Manifest**: A JSON file describing a web application's metadata (name, icons,
theme color, display mode) enabling it to be installed and behave more like a native app
("Progressive Web App" / PWA capability).

## 15.14 Sample Take-Home Project Spec & Evaluation Rubric

Many companies (especially startups, per Part 15.12) assess candidates via a take-home
project instead of (or alongside) live coding rounds. Below is a realistic example brief,
followed by the kind of rubric an interviewer would actually grade it against — use it as a
practice project applying everything from Parts 1-12.

### Example Brief: "Build a Movie Search App"

> Using the public OMDb API (or any similar public API), build a small single-page app that
> lets a user search for movies by title, view a paginated list of results, and click into a
> result to see more details. You have 4-6 hours; submit a GitHub repo with a README
> explaining how to run it and any tradeoffs you made given the time constraint.
>
> Requirements:
> - A search input that queries the API as the user types (debounced).
> - A paginated or infinite-scrolled results list showing poster, title, and year.
> - Loading, empty, and error states for the search.
> - A details view showing more information about a selected movie (plot, cast, rating).
> - Responsive layout that works reasonably well on both mobile and desktop viewport widths.
> - At least a few automated tests covering core logic/components.
>
> You may use any frontend framework/library you're comfortable with. We care more about the
> quality of your decisions than which specific tools you chose.

### What a Strong Submission Actually Demonstrates

- **Debouncing the search input** (Part 4.9) rather than firing a request on every keystroke
  — and ideally handling the out-of-order-response race condition (Part 13.2) with an
  `AbortController`, even though the brief doesn't explicitly ask for it — this is exactly the
  kind of unprompted attention to detail that separates strong submissions.
- **Explicit, distinct UI for loading/empty/error states** (Part 15.9 mistake #11) — not just
  a happy-path implementation that breaks or shows nothing useful when the API returns zero
  results or fails.
- **Semantic HTML and basic accessibility** (Part 2, Part 12) — real `<label>`s on the search
  input, a real `<button>` for pagination controls, reasonable focus management when
  navigating to the details view.
- **A sensible, if small, component structure** — a `SearchBar`, a `ResultsList`, a
  `ResultCard`, a `MovieDetails` view, rather than one 400-line monolithic component with
  everything inline.
- **At least a few meaningful tests** (Part 10) — testing the debounce behavior, a
  component rendering correctly given mock data, and an error state rendering correctly given
  a mocked failed request; quality and relevance matter far more than raw test count.
- **A README that's honest about tradeoffs** — e.g., "I didn't implement true infinite scroll
  virtualization since the API returns at most 10 results per page, but I documented how I'd
  approach it if result sets were much larger" demonstrates the same system-design thinking as
  Part 13, applied to your own real submission.
- **Reasonably performant image loading** — `loading="lazy"` on poster images (Part 2.5),
  explicit `width`/`height` to avoid layout shift (Part 11.1, Part 15.9 mistake #27).

### Common Reasons Take-Homes Score Poorly

- No error/empty/loading states at all — the app only "works" for the happy path.
- Debouncing forgotten or implemented incorrectly (firing on every keystroke, or firing a
  request on literally every render due to a missing/incorrect `useEffect` dependency array).
- Zero automated tests, or tests that only check trivial things (e.g., "renders without
  crashing") without covering any actual logic.
- Inaccessible markup — `<div onClick>` for buttons, images without `alt`, unlabeled inputs
  (Part 15.9 mistakes #16, #20, #31).
- A README that doesn't explain how to actually run the project, or omits any discussion of
  tradeoffs/what you'd do with more time — take-homes are explicitly time-boxed, and
  reviewers want to see that you understood and communicated your scoping decisions rather
  than either over-engineering or silently cutting corners.
- Committing `node_modules`, API keys, or other files that shouldn't be in version control —
  a small detail, but one reviewers notice as a signal of overall engineering hygiene.

## 15.15 Annotated Code Review Examples — Before & After

Reviewing real diffs (with reviewer comments) is one of the fastest ways to internalize good
practice. Below are 10 realistic "before/after" examples, each with the kind of comment a
thoughtful senior reviewer would actually leave.

### Example 1: Debounce Missing on a Search Handler

```jsx
// BEFORE
function SearchBox() {
  const [query, setQuery] = useState('');
  function handleChange(e) {
    setQuery(e.target.value);
    fetchResults(e.target.value); // fires on EVERY keystroke
  }
  return <input value={query} onChange={handleChange} />;
}
```
> **Reviewer comment**: "This fires a network request on every keystroke — for a fast typist
> that's a request every ~100ms, which will hammer the backend and produce out-of-order
> responses. Debounce this, and consider an AbortController for the race condition too."

```jsx
// AFTER
function SearchBox() {
  const [query, setQuery] = useState('');
  const debouncedFetch = useMemo(() => debounce((q) => fetchResults(q), 300), []);
  function handleChange(e) {
    setQuery(e.target.value);
    debouncedFetch(e.target.value);
  }
  return <input value={query} onChange={handleChange} />;
}
```

### Example 2: Mutating State Directly

```jsx
// BEFORE
function addTodo(text) {
  todos.push({ id: Date.now(), text, done: false });
  setTodos(todos);
}
```
> **Reviewer comment**: "This mutates the existing array in place — `setTodos(todos)` passes
> the exact same reference React already has, so it won't detect a change and won't
> re-render. Create a new array instead."

```jsx
// AFTER
function addTodo(text) {
  setTodos(prev => [...prev, { id: Date.now(), text, done: false }]);
}
```

### Example 3: Missing `useEffect` Cleanup

```jsx
// BEFORE
useEffect(() => {
  const id = setInterval(() => refreshData(), 5000);
}, []);
```
> **Reviewer comment**: "No cleanup here — this interval keeps running even after the
> component unmounts, and will eventually try to call `refreshData` (which likely calls
> `setState`) on an unmounted component. Please return a cleanup function."

```jsx
// AFTER
useEffect(() => {
  const id = setInterval(() => refreshData(), 5000);
  return () => clearInterval(id);
}, []);
```

### Example 4: Overusing `any` in TypeScript

```ts
// BEFORE
function processApiResponse(data: any) {
  return data.results.map((r: any) => r.name);
}
```
> **Reviewer comment**: "This defeats the purpose of TypeScript here — if the API shape ever
> changes, we get a runtime crash instead of a compile-time warning. Please define a proper
> interface for the response shape, even a partial one covering just what we use."

```ts
// AFTER
interface ApiResponse {
  results: { name: string; id: number }[];
}
function processApiResponse(data: ApiResponse) {
  return data.results.map(r => r.name);
}
```

### Example 5: Index as Key in a Reorderable List

```jsx
// BEFORE
{items.map((item, index) => <ListRow key={index} item={item} />)}
```
> **Reviewer comment**: "This list supports drag-to-reorder, so using the array index as the
> key will cause React to misassociate state across reorders — please use `item.id` instead."

```jsx
// AFTER
{items.map((item) => <ListRow key={item.id} item={item} />)}
```

### Example 6: Layout-Triggering Animation Property

```css
/* BEFORE */
.card { transition: left 0.3s ease, width 0.3s ease; }
.card.expanded { left: 0; width: 100%; }
```
> **Reviewer comment**: "Animating `left`/`width` forces a layout recalculation on every
> frame — please switch to `transform`/a scale-based approach so this can run on the
> compositor thread instead."

```css
/* AFTER */
.card { transition: transform 0.3s ease; transform-origin: left center; }
.card.expanded { transform: scale(1.5); }
```

### Example 7: Unmemoized Context Value Causing Excess Re-renders

```jsx
// BEFORE
function AuthProvider({ children }) {
  const [user, setUser] = useState(null);
  return (
    <AuthContext.Provider value={{ user, setUser }}>
      {children}
    </AuthContext.Provider>
  );
}
```
> **Reviewer comment**: "`{ user, setUser }` is a new object every render of `AuthProvider`,
> so every consumer re-renders even when `user` itself hasn't changed. Please memoize it."

```jsx
// AFTER
function AuthProvider({ children }) {
  const [user, setUser] = useState(null);
  const value = useMemo(() => ({ user, setUser }), [user]);
  return <AuthContext.Provider value={value}>{children}</AuthContext.Provider>;
}
```

### Example 8: Unsanitized `innerHTML` from User Input

```jsx
// BEFORE
function Comment({ text }) {
  return <div dangerouslySetInnerHTML={{ __html: text }} />;
}
```
> **Reviewer comment**: "This renders raw user-submitted text as HTML — that's a stored XSS
> vulnerability if `text` ever contains a script tag or an `onerror` attribute. Either render
> it as plain text, or sanitize it with DOMPurify first if we genuinely need to support rich
> text."

```jsx
// AFTER
import DOMPurify from 'dompurify';
function Comment({ text }) {
  return <div dangerouslySetInnerHTML={{ __html: DOMPurify.sanitize(text) }} />;
}
```

### Example 9: Not Checking `res.ok`

```js
// BEFORE
async function getUser(id) {
  const res = await fetch(`/api/users/${id}`);
  return res.json();
}
```
> **Reviewer comment**: "If this returns a 404, `res.json()` will likely parse an error
> payload as if it were a valid user object, and calling code will crash confusingly further
> downstream. Please check `res.ok` and throw a clear error here instead."

```js
// AFTER
async function getUser(id) {
  const res = await fetch(`/api/users/${id}`);
  if (!res.ok) throw new Error(`Failed to fetch user ${id}: ${res.status}`);
  return res.json();
}
```

### Example 10: Missing Accessible Name on an Icon-Only Button

```jsx
// BEFORE
<button onClick={closeModal}>✕</button>
```
> **Reviewer comment**: "A screen reader announces this as just '✕' or nothing meaningful at
> all — please add an accessible label describing the action."

```jsx
// AFTER
<button onClick={closeModal} aria-label="Close dialog">✕</button>
```

## 15.16 Extra Coding Challenges (Extending Part 14.8)

### Challenge 13: Implement a Simplified Promise From Scratch

**Problem**: Implement a `MyPromise` class supporting `resolve`/`reject`, `.then()` chaining,
and the pending/fulfilled/rejected state machine, without using the native `Promise`.

```js
class MyPromise {
  #state = 'pending';
  #value;
  #callbacks = [];

  constructor(executor) {
    const resolve = (value) => this.#settle('fulfilled', value);
    const reject = (reason) => this.#settle('rejected', reason);
    try {
      executor(resolve, reject);
    } catch (err) {
      reject(err);
    }
  }

  #settle(state, value) {
    if (this.#state !== 'pending') return; // can only settle once
    this.#state = state;
    this.#value = value;
    queueMicrotask(() => {
      this.#callbacks.forEach(cb => cb());
      this.#callbacks = [];
    });
  }

  then(onFulfilled, onRejected) {
    return new MyPromise((resolve, reject) => {
      const handle = () => {
        try {
          if (this.#state === 'fulfilled') {
            const result = onFulfilled ? onFulfilled(this.#value) : this.#value;
            resolve(result);
          } else if (this.#state === 'rejected') {
            if (onRejected) resolve(onRejected(this.#value));
            else reject(this.#value);
          }
        } catch (err) {
          reject(err);
        }
      };
      if (this.#state === 'pending') this.#callbacks.push(handle);
      else queueMicrotask(handle);
    });
  }

  catch(onRejected) {
    return this.then(null, onRejected);
  }
}

// Test
new MyPromise((resolve) => setTimeout(() => resolve(42), 100))
  .then(v => v * 2)
  .then(v => console.log(v)); // 100ms later: 84
```
**Discussion point**: this deliberately mirrors the real Promises/A+ spec's core shape —
`queueMicrotask` is what correctly makes `.then()` callbacks run as microtasks (Part 4.7)
rather than synchronously, matching native Promise behavior.

### Challenge 14: Implement `Array.prototype.reduce` From Scratch

**Problem**: Implement `myReduce(arr, callback, initialValue)` matching native `reduce`'s
behavior, including the case where `initialValue` is omitted.

```js
function myReduce(arr, callback, initialValue) {
  const hasInitial = arguments.length >= 3;
  let acc = hasInitial ? initialValue : arr[0];
  const startIndex = hasInitial ? 0 : 1;

  if (!hasInitial && arr.length === 0) {
    throw new TypeError('Reduce of empty array with no initial value');
  }

  for (let i = startIndex; i < arr.length; i++) {
    acc = callback(acc, arr[i], i, arr);
  }
  return acc;
}

// Test
console.log(myReduce([1, 2, 3, 4], (acc, n) => acc + n, 0));  // 10
console.log(myReduce([1, 2, 3, 4], (acc, n) => acc + n));      // 10 (no initial value, starts from arr[0])
console.log(myReduce([5], (acc, n) => acc + n));                // 5 (single element, no initial value)
```
**Discussion point**: correctly handling the "no initial value provided" case (using the
first element as the accumulator's starting point and iterating from index 1) is exactly what
separates a superficial implementation from one that matches real spec behavior — a common
follow-up interviewers ask for after a naive first pass.

### Challenge 15: Implement a Minimal Client-Side Router (Path Matching)

**Problem**: Given a list of route patterns like `/users/:id` and a real path like
`/users/42`, implement a `matchRoute(pattern, path)` function that returns the extracted
params or `null` if no match.

```js
function matchRoute(pattern, path) {
  const patternParts = pattern.split('/').filter(Boolean);
  const pathParts = path.split('/').filter(Boolean);

  if (patternParts.length !== pathParts.length) return null;

  const params = {};
  for (let i = 0; i < patternParts.length; i++) {
    const patternPart = patternParts[i];
    const pathPart = pathParts[i];

    if (patternPart.startsWith(':')) {
      params[patternPart.slice(1)] = pathPart; // dynamic segment, capture it
    } else if (patternPart !== pathPart) {
      return null; // static segment mismatch
    }
  }
  return params;
}

// Test
console.log(matchRoute('/users/:id', '/users/42'));            // { id: '42' }
console.log(matchRoute('/users/:id/posts/:postId', '/users/42/posts/7')); // { id: '42', postId: '7' }
console.log(matchRoute('/users/:id', '/posts/42'));             // null
console.log(matchRoute('/about', '/about'));                    // {} (static match, no params)
```
**Discussion point**: real routers (React Router, Next.js) add substantially more — optional
segments, wildcard/catch-all routes, nested route matching with partial matches, and route
ranking/precedence when multiple patterns could match the same path — but this core
segment-by-segment comparison is the conceptual heart of how path matching actually works.

### Challenge 16: Implement a Rate Limiter (Token Bucket)

**Problem**: Implement a `RateLimiter` class with `tryConsume()` that returns `true` if a
request is allowed (within `maxTokens` per `refillIntervalMs`), or `false` if the caller
should be rate-limited.

```js
class RateLimiter {
  #maxTokens;
  #tokens;
  #refillIntervalMs;
  #lastRefill;

  constructor(maxTokens, refillIntervalMs) {
    this.#maxTokens = maxTokens;
    this.#tokens = maxTokens;
    this.#refillIntervalMs = refillIntervalMs;
    this.#lastRefill = Date.now();
  }

  #refill() {
    const now = Date.now();
    const elapsed = now - this.#lastRefill;
    const tokensToAdd = Math.floor((elapsed / this.#refillIntervalMs) * this.#maxTokens);
    if (tokensToAdd > 0) {
      this.#tokens = Math.min(this.#maxTokens, this.#tokens + tokensToAdd);
      this.#lastRefill = now;
    }
  }

  tryConsume() {
    this.#refill();
    if (this.#tokens > 0) {
      this.#tokens--;
      return true;
    }
    return false;
  }
}

// Test: allow 5 requests per second
const limiter = new RateLimiter(5, 1000);
for (let i = 0; i < 7; i++) {
  console.log(`Request ${i + 1}: ${limiter.tryConsume() ? 'allowed' : 'rate-limited'}`);
}
// First 5 requests: allowed. Requests 6-7: rate-limited (until tokens refill over time).
```
**Discussion point**: the token bucket algorithm is a real, widely-used rate-limiting
strategy (used by many actual API gateways) — a frontend-relevant application is
client-side-throttling outgoing requests to a third-party API with a strict rate limit,
complementing (not replacing) any server-side rate limiting.

### Challenge 17: Implement a Simple Pub-Sub State Manager With Middleware

**Problem**: Extend Challenge 11's mini-store (Part 14.8) to support middleware — functions
that can intercept, log, or transform actions before they reach the reducer, mirroring
Redux's middleware model.

```js
function createStoreWithMiddleware(reducer, initialState, middlewares = []) {
  let state = initialState;
  const listeners = new Set();

  function dispatch(action) {
    state = reducer(state, action);
    listeners.forEach(listener => listener(state));
  }

  // Compose middlewares: each wraps the next, forming a chain around the real dispatch
  const chainedDispatch = middlewares.reduceRight(
    (next, middleware) => middleware(store)(next),
    dispatch
  );

  const store = {
    getState: () => state,
    dispatch: (action) => chainedDispatch(action),
    subscribe: (listener) => { listeners.add(listener); return () => listeners.delete(listener); },
  };
  return store;
}

// Example middleware: logs every action before/after it's processed
const loggerMiddleware = (store) => (next) => (action) => {
  console.log('Dispatching:', action);
  next(action);
  console.log('New state:', store.getState());
};

// Test
function counterReducer(state = { count: 0 }, action) {
  switch (action.type) {
    case 'INCREMENT': return { count: state.count + 1 };
    default: return state;
  }
}
const store = createStoreWithMiddleware(counterReducer, { count: 0 }, [loggerMiddleware]);
store.dispatch({ type: 'INCREMENT' });
// Logs: "Dispatching: { type: 'INCREMENT' }" then "New state: { count: 1 }"
```
**Discussion point**: this `reduceRight`-based composition is genuinely how Redux's own
`applyMiddleware` works internally — recognizing and explaining this connection is a strong
signal that you understand Redux's internals, not just its public API surface.

## 15.17 Extra Rapid-Fire Q&A Round 2 (40 More Questions)

1. **Q: What does `Object.freeze` fail to protect against, specifically?** A: Nested objects
   inside the frozen object remain fully mutable — freezing is shallow, not deep, so
   `Object.freeze(obj); obj.nested.x = 5;` still succeeds (Part 14.2 Q14).
2. **Q: Why does `typeof NaN` return `'number'`?** A: `NaN` ("Not a Number") is, perhaps
   counter-intuitively, a special value of the `number` type in JavaScript's type system, used
   to represent the result of invalid numeric operations.
3. **Q: What's the difference between `Array.prototype.slice` and `Array.prototype.splice`?**
   A: `slice` is non-mutating and returns a shallow copy of a range; `splice` mutates the
   original array in place, removing/inserting elements and returning the removed ones.
4. **Q: Why is `for...in` generally discouraged for iterating arrays?** A: It iterates over
   all enumerable properties, including inherited ones and any custom properties added to the
   array object, and doesn't guarantee numeric index order — `for...of` or array methods are
   safer and clearer for arrays specifically.
5. **Q: What does the spread operator do differently on an object vs. an array?** A:
   `{...obj}` performs a shallow merge/copy of enumerable own properties; `[...arr]` expands
   an iterable into individual elements — same syntax, different underlying mechanism (object
   property enumeration vs. the iterator protocol).
6. **Q: What is "tree shaking" unable to remove, even with perfect static analysis?** A: Code
   with side effects at the module level (e.g., a top-level function call that mutates a
   global, or a CSS import) can't be safely removed even if its export is unused, since
   removing it could change program behavior — this is why `package.json`'s `"sideEffects":
   false` field exists, to explicitly tell bundlers a package has none.
7. **Q: What's the difference between `Object.assign({}, a, b)` and `{...a, ...b}`?** A:
   Functionally nearly identical for plain objects (both perform a shallow merge, later
   sources win on key conflicts) — `Object.assign` additionally allows mutating an existing
   target object in place if you don't pass `{}` as the first argument, while spread always
   creates a new object.
8. **Q: Why might two seemingly identical React elements NOT be considered equal by
   `React.memo`'s default comparison?** A: `React.memo`'s default shallow comparison checks
   prop equality via `Object.is`, which is reference-based for objects/arrays/functions — two
   structurally identical but separately-created objects are never `Object.is`-equal.
9. **Q: What happens if you call `setState` with the exact same value it already has?** A:
   React (for primitive state values compared via `Object.is`) will bail out of re-rendering
   that component (though it may still run its own render function once to check) — an
   internal optimization sometimes referred to as "bailing out."
10. **Q: What's the purpose of the second argument to `useState`'s initializer function form
    (`useState(() => expensiveComputation())`)?** A: The function form (a "lazy initializer")
    ensures the expensive computation only runs once, on the very first render, rather than
    being recomputed (and discarded) on every single render the way `useState(expensiveComputation())`
    would.
11. **Q: Why can't you call `useState` conditionally, even if the condition is guaranteed to
    be stable after the first render?** A: The Rules of Hooks require hooks to be called in
    the exact same order every render, unconditionally — React's internal implementation
    associates hook state with call order/position, not with any name or identity, so any
    conditional hook call risks breaking that association (Part 7.6).
12. **Q: What's the difference between a "controlled" and "uncontrolled" component in the
    general sense (beyond just form inputs)?** A: A controlled component's behavior/state is
    fully dictated by props passed from a parent (the parent "controls" it); an uncontrolled
    component manages some of its own internal state independently — the same controlled/
    uncontrolled spectrum applies to custom components generally, not just native form inputs
    (Part 7.9).
13. **Q: What does "colocation" mean as a React code-organization principle?** A: Keeping
    related code (a component, its styles, its tests, its specific hooks) physically close
    together in the file structure, rather than organizing by technical layer (all components
    in one folder, all styles in another) — generally considered easier to navigate and
    refactor for feature-sized codebases.
14. **Q: Why does GSAP's `stagger` sometimes feel "wrong" with a very large number of
    elements?** A: A large `each` value multiplied across hundreds of elements can produce an
    excessively long total animation duration; for large collections, reducing `each` or
    capping the total stagger duration (via GSAP's `amount` option, which spreads a fixed
    total duration across however many elements exist) usually feels better.
15. **Q: What is the difference between `ScrollTrigger`'s `start: 'top top'` and
    `start: 'top center'`?** A: `'top top'` triggers when the element's top edge reaches the
    very top of the viewport; `'top center'` triggers earlier, when the element's top edge
    reaches the vertical center of the viewport (Part 8.6).
16. **Q: Why would you choose `IntersectionObserver` over `ScrollTrigger` for a simple
    fade-in-on-scroll effect?** A: For a genuinely simple one-shot trigger with no scrubbing/
    pinning/sequencing needs, a plain `IntersectionObserver` (Part 6.6) avoids pulling in
    GSAP's ScrollTrigger plugin entirely, keeping the bundle smaller — reach for ScrollTrigger
    specifically when you need scrubbing, pinning, or coordinated multi-element timelines.
17. **Q: What is "paint containment" (`contain: paint`) used for?** A: A CSS property hinting
    to the browser that an element's descendants won't visually overflow its bounds, allowing
    the browser to skip repainting areas outside it during certain updates — a lesser-known
    but real performance optimization for isolated, self-contained UI regions.
18. **Q: Why is `<link rel="preconnect">` valuable for third-party resources specifically?**
    A: It lets the browser establish the DNS/TCP/TLS connection to that origin ahead of time,
    before the resource is actually requested, shaving real time off requests to
    frequently-used third-party origins (fonts, analytics, CDNs) (Part 11.1).
19. **Q: What's the practical difference between `sessionStorage` and an in-memory JS
    variable for storing temporary state?** A: `sessionStorage` survives a full page reload
    within the same tab; a plain JS variable is lost on any reload/navigation, since JS state
    doesn't persist across page loads at all (Part 6.4).
20. **Q: Why does `Array.prototype.sort()` behave unexpectedly on numbers without a compare
    function?** A: The default sort converts elements to strings and compares them
    lexicographically, so `[10, 2, 1].sort()` produces `[1, 10, 2]`, not numeric order — always
    pass an explicit compare function (`(a, b) => a - b`) for numeric sorting.
21. **Q: What is a "render prop" and why has it largely fallen out of favor?** A: A pattern
    of passing a function as a prop that returns JSX, used to share logic between components
    before hooks existed; it's largely been replaced by custom hooks, which achieve the same
    logic-sharing goal with less nesting/wrapping boilerplate (Part 7.6).
22. **Q: What's the difference between `React.StrictMode`'s effects in development vs.
    production builds?** A: Strict Mode's extra checks (double-invoking certain functions,
    including effects, to surface missing-cleanup bugs) only run in development builds; they
    have zero effect in production builds, so any bug that "only shows up in Strict Mode" is
    a real latent bug, not a false positive, even though production won't visibly double-fire
    it the same way.
23. **Q: Why might a form's submit button remain disabled even though all fields appear
    filled in?** A: Common causes include a validation state that wasn't updated on the last
    field change (a stale closure/missing dependency, Part 7.4), or a validation check with an
    off-by-one/incorrect condition (e.g., checking `length > 8` when the requirement is
    actually `length >= 8`).
24. **Q: What's the difference between "hard" and "soft" navigation in an SPA context?** A:
    A hard navigation is a full page reload (new HTML document request); a soft navigation is
    a client-side route change handled by the SPA's router, updating the URL via the History
    API without reloading the page (Part 7.11).
25. **Q: Why should a `key` prop never be derived from an item's array position even if that
    array is never reordered, if items can still be inserted/removed from the middle?** A:
    Inserting/removing anywhere except the very end still shifts every subsequent item's
    index, causing the same state-misassociation problem as reordering (Part 7.7).
26. **Q: What's the main tradeoff of shipping a component library as CSS-in-JS versus plain
    CSS files?** A: CSS-in-JS colocates styles with logic and enables truly dynamic,
    prop-driven styling without manual class toggling, at the cost of a runtime/build
    dependency and (for some libraries) a small runtime style-injection overhead; plain CSS
    has zero runtime cost but requires more manual work to achieve the same dynamic styling
    (Part 3.12).
27. **Q: Why does `Number.parseInt('08')` sometimes surprise people, and how do you avoid the
    issue?** A: Historically, a leading zero could be interpreted as an octal radix in older
    engines; modern engines default to base 10, but it's still best practice to always pass an
    explicit radix (`parseInt('08', 10)`) to remove any ambiguity entirely.
28. **Q: What is a "positive" vs a "negative" lookahead in a regular expression, at a high
    level?** A: A positive lookahead (`(?=...)`) asserts that a pattern *does* follow at a
    given position without consuming it; a negative lookahead (`(?!...)`) asserts it does
    *not* follow — both are used for conditional matching without including the lookahead
    text itself in the match.
29. **Q: Why is `document.querySelectorAll` result a "static" NodeList rather than "live"?**
    A: `querySelectorAll` snapshots the matching elements at the moment it's called; it will
    not automatically include elements added to the DOM afterward, unlike some older "live"
    collections (`getElementsByClassName`) which do update automatically.
30. **Q: What's the risk of relying purely on `:hover` for revealing critical interactive
    controls?** A: Touch devices have no true hover state, so hover-only-revealed controls
    (like a hidden "delete" button that only appears on hover) become difficult or impossible
    to discover/use on mobile — always provide a touch-accessible alternative.
31. **Q: What does "progressive enhancement" mean in the context of a JavaScript-heavy SPA?**
    A: Ensuring a reasonable baseline experience exists even if JS fails to load or execute
    (working forms with real `action`/`method` attributes as a fallback, server-rendered
    critical content) — increasingly de-emphasized in fully JS-dependent SPAs, but still a
    relevant consideration for critical flows and for resilience against JS errors.
32. **Q: What's the difference between `element.scrollIntoView()`'s `block` and `inline`
    options?** A: `block` controls vertical alignment (`'start'`/`'center'`/`'end'`/
    `'nearest'`) and `inline` controls horizontal alignment — relevant for precisely
    positioning a scrolled-to element within the viewport rather than just "somewhere visible."
33. **Q: Why might `useCallback` fail to prevent a child re-render even though the callback
    reference is stable?** A: If the child isn't wrapped in `React.memo` at all, memoizing the
    callback prop alone does nothing — `useCallback` only helps in combination with a memoized
    child component that actually checks its props (Part 7.7).
34. **Q: What's a practical reason to avoid very deeply nested Context providers (a "provider
    pyramid")?** A: Beyond readability, each nested provider is a potential re-render boundary
    — deeply nested, frequently-changing providers can create hard-to-trace re-render cascades;
    combining related providers or moving to a dedicated state library often simplifies this.
35. **Q: Why does `Array.prototype.includes` handle `NaN` correctly while `indexOf` does
    not?** A: `includes` uses the SameValueZero algorithm (which treats `NaN` as equal to
    itself); `indexOf` uses strict equality (`===`), under which `NaN === NaN` is `false`
    (Part 4.1, Part 15.9 mistake #40).
36. **Q: What does "shifting left" mean in the context of testing/QA?** A: Moving quality
    checks (tests, linting, accessibility audits) earlier in the development process — running
    them locally/in CI before merge — rather than relying solely on manual QA late in the
    cycle, catching issues when they're cheaper and faster to fix.
37. **Q: Why might a `fetch` request appear to hang indefinitely with no error and no
    response?** A: Common causes include a server that never responds (no timeout configured
    client-side), or — specifically in development — a proxy/CORS preflight (`OPTIONS`
    request) failing silently; always set an explicit timeout (`AbortSignal.timeout(...)`,
    Part 6.3) so a hung request fails predictably instead of hanging forever.
38. **Q: What's the difference between "eager" and "lazy" loading in the context of code
    splitting?** A: Eager loading includes a chunk in the initial bundle/download regardless
    of whether it's immediately needed; lazy loading (`React.lazy`/dynamic `import()`, Part
    7.7) defers downloading a chunk until the exact moment it's actually needed.
39. **Q: Why does a `useEffect` that depends on an object prop sometimes re-run more than
    expected, even if the object's contents never actually change?** A: If the parent creates
    a new object literal on every render (e.g., an inline `{ x: 1 }` passed as a prop) instead
    of a stable memoized reference, `Object.is` in the dependency comparison always considers
    it "changed," triggering the effect every render (Part 7.4, similar root cause to Part
    15.9 mistake #17).
40. **Q: What is the single biggest mindset shift going from "I can make things work" to
    "I write production-quality frontend code"?** A: Consistently considering the *edge
    cases* (empty/loading/error states, accessibility, cleanup, race conditions) as a default
    part of implementing any feature, rather than as optional afterthoughts added only when
    explicitly requested — exactly the habit this entire guide has tried to model throughout
    every code example.

---
<!-- APPEND_MARKER: DO NOT REMOVE -->

