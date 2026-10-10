# Avenue Vision: 16 art directions (build brief)

## Why this brief exists

The last 36 templates all looked the same. Every one used one anatomy: a utility bar, a header, a split hero with a form card, rows of 4 icon cards, dashed coupons, 3 review cards, town chips, a 2-column FAQ and a 4-column dark footer. Only the fonts and colors changed. The client said, correctly, that they all look like the same contractor template.

This round, each page is built from a REAL design system taken from a style-reference library Styles (a library of DESIGN.md files extracted from top websites). The page must look like a sibling of its reference site, used for a home-service contractor. If you put it next to the earlier templates, nobody should think they came from the same builder.

The earlier templates are in these contact sheets. Look at one so you know what NOT to make:
`/tmp/claude-0/-home-claude/79cb5c0e-ffb6-51d2-8a76-be73d1c9c066/scratchpad/shots/vsheet-0.png`

## Step 1: study your references (do this properly)

For each a style-reference library style ID you are given:
1. Get its DESIGN.md:
   `python3 /tmp/claude-0/-home-claude/79cb5c0e-ffb6-51d2-8a76-be73d1c9c066/scratchpad/refs/extract_md.py <STYLE_ID> > /tmp/claude-0/-home-claude/79cb5c0e-ffb6-51d2-8a76-be73d1c9c066/scratchpad/refs/<STYLE_ID>.md`
   Then read the whole file. It covers colors, typography, spacing, components, layout principles and "do / don't" rules.
2. Get its screenshot and LOOK at it with your image-reading tool. The page's `og:image` meta tag holds the screenshot URL:
   `curl -sS https://[reference library]/<STYLE_ID> | grep -o '<meta property="og:image" content="[^"]*"'`
   Then download that URL with curl into `.../scratchpad/refs/` and Read the image.

Then write a short art-direction note for yourself (10 lines): grid and layout system, type pairing and scale, color roles, surface treatment, signature moves (the 3 things that make the reference recognizable), and how a contractor's SEO content will live inside this style without breaking it.

## Step 2: build

- Layout comes from the reference, not from habit. Do NOT use the banned anatomy above. Invent the section structure the reference style would use for this business. For example: a broadsheet uses a masthead, columns and datelines; a bento uses tiles; a map console uses a map with side panels; a catalogue uses product spec sheets.
- Proprietary fonts: use the Google Fonts substitute that the DESIGN.md names (or the closest Google Font). Never load fonts from anywhere except fonts.googleapis.com.
- Borrow the design SYSTEM: type scale, grid, spacing, color roles, component shapes, motion feel. Never the brand: no logos, names, slogans, product photos or wording from the reference site. If the reference's signature brand color is iconic (for example a sports-car brand yellow or a sports-car brand red), shift the hue so it stays a sibling, not a copy.
- Real photography is available. Each trade has a pool of free-licensed Unsplash photos at `bv/project/img/<trade>/NN.jpg`. Look at the labelled contact sheet first: `/tmp/claude-0/-home-claude/79cb5c0e-ffb6-51d2-8a76-be73d1c9c066/scratchpad/photosheets/<trade>.jpg`. Use `<img src="img/<trade>/NN.jpg" alt="…" width="…" height="…" style="…object-fit: cover…">` with a relative src exactly in that form. Hero image: no lazy loading. Others: `loading="lazy"`. Use 3–7 photos, chosen and cropped the way the reference treats imagery (full bleed, plates, rounded tiles, duotone via a CSS filter, and so on). You may also use inline SVG illustration, maps and diagrams where the style calls for them.
- The canvas board is 1280 wide. The page must also work at 390 wide with no sideways scroll.

## SEO and conversion checklist (content that must exist, in the style's own form)

These are things the page must CONTAIN, not sections to stack. Fit each one into the style. A broadsheet can put NAP in its masthead dateline; a bento can make the FAQ a tile; a map console can list towns as map labels.
- One H1 naming the service and the city.
- The phone as a `tel:` link, visible in the first screen, plus one primary call to action that is a 2–3 word Title Case verb ("Book a Visit", "Get My Price"). Never "Submit", "Learn More" or "Click Here".
- Each core service (5–8) linked to its own page, with the slug visible somewhere, e.g. `/water-heater-repair`.
- Price guidance: ranges like `$[LOW]–$[HIGH]` or "from $[PRICE]".
- Proof: `[RATING]` from `[COUNT]` Google reviews, with a recency line ("Newest review [DAYS] days ago"). Never invent a testimonial in a person's voice. Review quotes are `[Google review, pulled at build time]` attributed to `[Reviewer], [Town]`.
- Towns served as links (`/areas/<town>`), at least 6 real towns near the assigned city.
- NAP: business name, `[STREET ADDRESS]` or "Service-area business", phone, `[HOURS]`, license `[LICENSE NO.]`.
- 3–4 FAQs phrased the way people search, with the answers visible in the HTML.
- Facts only the owner can supply stay in brackets: `[YEARS]`, `[PRICE]`, `[OWNER NAME]`, `[CERTIFICATION]`.
- Plain, confident copy written as a local tech talking at the door. No emoji, no exclamation marks, no "Welcome to our website", no "best-in-class" adjectives. Use numbers.
- A muted line at the very bottom: `Avenue Vision · D__ · [direction name] · style refs withheld`.

## File format (Design Component .dc.html)

Copy the skeleton of this working example exactly: doctype, `<script src="./support.js"></script>` in head, `<x-dc>`, `<helmet>`, the trailing script block.
`/tmp/claude-0/-home-claude/79cb5c0e-ffb6-51d2-8a76-be73d1c9c066/scratchpad/bv/project/PalmettoSite.dc.html`

- `<helmet>` holds ONE Google Fonts css2 `<link>` (use `&amp;` between families) and ONE `<style>` block. Unlike before, you MAY use real CSS in that style block: class rules, hover and focus states, `@media` breakpoints, `clamp()`, CSS variables, grid areas. Prefix every class with your file id (e.g. `.d07-hero`) so styles never leak between boards. Keep `body{margin:0}`. Inline styles are fine too.
- Close every element. Quote every attribute. No `<sc-for>`/`<sc-if>` anywhere (write repeated markup literally).
- No `<iframe>`, no external images, no JS libraries. Images come only from `img/...` relative paths.
- Trailing block: `<script type="text/x-dc" data-dc-script data-props='{"$preview":{"width":1280,"height":H}}'>class Component extends DCLogic { renderVals() { return {}; } }</script>`, where H is the measured page height at 1280, rounded up to the next 100. The data-props JSON must have no single quotes.
- Text contrast at least 4.5:1 (3:1 for 24px+). Tap targets at least 44px.
- Write files to `/tmp/claude-0/-home-claude/79cb5c0e-ffb6-51d2-8a76-be73d1c9c066/scratchpad/bv/project/<FILE>`. Do not touch any other file. Do not publish.

## Step 3: look at it, critique it, fix it (required, at least one full round)

Render with Python Playwright (installed; Chromium is at /opt/pw-browsers). Use `page.goto('file://...')` on a TEMP COPY saved next to the real file in `bv/project/` (so `img/...` paths resolve). In the copy, remove the support.js line and the trailing text/x-dc script; delete the copy afterwards. Take three screenshots: the first 900px at 1280 wide, the full page at 1280, and the full page at 390. Measure `document.documentElement.scrollHeight` and `scrollWidth`. Read the screenshots next to the reference screenshot and ask honestly:
- Would a a style-reference library curator file this next to its reference? Name the 3 signature moves and confirm each one is visible.
- Does any part fall back to the banned anatomy? Replace it.
- Is anything broken: overflow, overlaps, unreadable text, empty gaps, a broken image?
Fix, re-render and look again. Do at least one revision round.

## Reply (under 200 words per page)

The file name, the direction, the references used (name and ID), the 3 signature moves you carried over, how the SEO checklist lives in the style, the photos used, the measured height, and anything you could not do.
