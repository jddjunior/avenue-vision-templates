# Avenue Vision contractor site templates: build brief

You are building homepage designs for a set of 10 website templates that Avenue Vision (an AI website builder for local trade contractors) will generate SEO-strong contractor sites from. Each template is ONE artboard file: a full desktop homepage (1280 px wide on the canvas, fluid) for a fictional sample business, in that template's own visual skin. The structure is the template; the skin shows one way a contractor could look in it.

Write each file with your file-writing tool at:
`/tmp/claude-0/-home-claude/79cb5c0e-ffb6-51d2-8a76-be73d1c9c066/scratchpad/bv/project/<FILENAME>`
Do NOT publish, do not use the Artifact tool, do not run shell scripts that generate the file. Do not edit any other file in that folder.

## 1. File format (a "Design Component" .dc.html). Read the working example first.

Read this finished example and copy its skeleton exactly (doctype, head, the `support.js` line, `<x-dc>`, `<helmet>`, the trailing script block):
`/tmp/claude-0/-home-claude/79cb5c0e-ffb6-51d2-8a76-be73d1c9c066/scratchpad/bv/project/PalmettoSite.dc.html`
The full format reference is at
`/tmp/claude-0/-home-claude/79cb5c0e-ffb6-51d2-8a76-be73d1c9c066/scratchpad/artifact-files/d185c87a-f2fe-409b-974d-baa4bbc01361/artifact-type/reference/format.md`

Rules that fail silently if broken:
- Keep `<script src="./support.js"></script>` in `<head>` exactly.
- `<helmet>` holds ONLY one Google Fonts `css2` `<link>` (use `&amp;` between families) and `<style>body{margin:0}</style>`. No other CSS anywhere: every style is an inline `style="…"` attribute.
- Close every non-void element. Quote every attribute.
- The root is `<div style="width: 100%; …">` with the page's background, text color and font-family. No px width on the root. Inner containers use `max-width: 1200px; margin: 0 auto; padding: … 40px`.
- Layout with flex or grid plus `gap`. Card rows use `display: grid; grid-template-columns: repeat(auto-fit, minmax(min(260px, 100%), 1fr))` (never a fixed `repeat(3, 1fr)`), so the page stacks on phones. Two-column blocks use the same auto-fit pattern with `min(440px, 100%)`.
- Tables: write every `<tr>` literally. Never put `<sc-for>` or `<sc-if>` inside `<table>`, `<tbody>` or `<tr>`. Simplest: do not use `<sc-for>` at all; write all repeated markup literally.
- `{{hole}}` is a dotted lookup into `renderVals()` only, never an expression. You may not need any holes. Always include the trailing block:
  `<script type="text/x-dc" data-dc-script data-props='{"$preview":{"width":1280,"height":H}}'>class Component extends DCLogic { renderVals() { return {}; } }</script>` where H is your best estimate of the page height at 1280 px (round up; over-tall is fine).
- `data-props` is single-quoted JSON: no raw single quotes inside it.
- No `<img>` (there are no image files): every photo is a labelled placeholder block, e.g. a tinted `<div>` with `aspect-ratio: 4 / 3`, a quiet pattern or nothing, and a small label "Photo: tech at a water heater in Carrollwood". This says what the real photo should be.
- Icons: small inline stroke `<svg>` (24 viewBox, `fill="none" stroke="currentColor"` or a hex). No emoji, no Unicode stars or symbols as icons. Stars are inline SVG paths.
- Real elements: links are `<a href="#">`, buttons `<button type="button">`, form fields are `<input>`/`<select>`/`<textarea>` inside a `<label>` (or with `for`/`id`). Phone links use `href="tel:+18135550118"` style hrefs.
- No `<iframe>`, `<object>`, `<embed>`, no external images, no network except the fonts link.
- Text contrast at least 4.5:1 (3:1 for 24px+). Check light text on brand colors and dark text on accent buttons. Touch targets at least 44px tall.
- Avoid gradient washes, glassmorphism, left-border accent cards and generic AI looks. Each template must have a distinct, committed visual identity (the skin given below).

## 2. Copy rules (from James's Avenue Local kit)

- Write like a trusted local tech talking to a homeowner at the door: plain, confident, specific. "We" for the company, "you" for the homeowner.
- The H1 and most H2s carry the city or region (local SEO): "Tampa Plumber, at Your Door Today", "Serving Brandon and Nearby".
- Buttons are verbs in Title Case, two or three words: "Call Now", "Book Online", "Get My Price", "Book My Measure". Never "Submit", "Learn More" or "Click Here".
- Intent rows start "I need…" / "I want…" / "I have…".
- Numbers persuade, not adjectives. Never "best-in-class", "world-class", "top-notch".
- Offers always carry a qualifier and an expiry in small print: "With completed repair. One per household. Expires 12/31/2026."
- Phone numbers are written `(813) 555-0118` (fictional 555-01xx numbers only).
- Facts only the owner can supply stay in brackets: `[LICENSE NO.]`, `[YEARS]`, `[PRICE]`, `[RATING]`, `[COUNT]`, `[OWNER NAME]`, `[HOURS]`, `[CERTIFICATION]`. Prices are `$[PRICE]` or ranges `$[LOW]–$[HIGH]`.
- Reviews: NEVER invent a testimonial in someone's voice. Review cards show stars (SVG), the quote as `[Google review, pulled at build time]`, attribution `[Reviewer], [Town]`, and the section shows a recency line like "Newest review [DAYS] days ago" and "[RATING] from [COUNT] Google reviews".
- No emoji, no exclamation marks, no "Welcome to our website".
- The sample business, its town and its phone are fictional (given below). Real Florida city and neighborhood names are fine.

## 3. Every template homepage includes (in its own form)

- A header: logo (simple inline SVG mark plus wordmark text), nav of at most 6 items, the phone as a tel link, one primary CTA.
- A hero with the city-first H1, one primary action and some evidence.
- A trust row (license, insured, guarantee, rating) adapted to the template.
- Services that link to their own service pages (show the URL slug as small text, e.g. `/drain-cleaning`, on the card or link) because one page per service is the top local ranking factor.
- Reviews section per the rules above.
- A service-area block: the towns served as links (`/areas/brandon`), optionally a ZIP checker.
- A short FAQ (4 questions phrased the way people search), visible in the HTML.
- A footer with NAP: business name, address `[STREET ADDRESS], City, FL [ZIP]` (or "Service area business" if no storefront), phone, `[HOURS]`, license `[LICENSE NO.]`, the towns served, links to services, and a legal line.
- Then the template's signature sections, described per template below. The signature sections are the point: make them genuinely good, specific, and visually strong.

Aim for 9–13 sections and a page height around 2800–4200 px at 1280. Quality over length.

When done, reply with: the filename(s), the section list top to bottom, the fonts and palette used, and anything you could not do.
