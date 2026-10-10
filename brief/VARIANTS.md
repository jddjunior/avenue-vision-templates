# 20 franchise-style template variations: build brief

Avenue Vision is an AI website builder. At launch its customers are single-location contractors who sign up themselves (self-serve). Generated sites will be built with Astro (server-rendered, almost no JavaScript), so each template must work as plain, semantic HTML.

Each variation studies ONE top-ranking franchise-group contractor website and turns what makes it convert and rank into a reusable template. The output is the homepage of a fictional single-location contractor, built in that franchise's design-system "language".

## Step 1: study the source (max ~6 minutes per source)

Use WebFetch on the source's national homepage and ONE local location page (find a Florida location if one exists; otherwise any location). One service page is optional. At most 4 fetches per source. If a fetch fails, try once more with another URL from that site, then work with what you have.

Write down, for yourself:
- Section order top to bottom on the home and location pages.
- Conversion mechanics: hero CTA style, ZIP or location finder, scheduling, coupons and offers, financing, guarantees, memberships, trust badges, review display, sticky elements, chat or text.
- Design-system language: header layout and density; type classification (condensed uppercase? rounded geometric sans? slab? serif?); heading scale; button shape (pill, square, rounded) and casing; card shape and borders or shadows; badge and seal styles; coupon styles; icon style (line, solid, duotone); how much white space; photo treatment (full bleed, rounded, angled, cut-outs); color ROLES (dark band, accent CTA, light ground).
- SEO gaps: what the site or location page lacks (service pages per location, price ranges, FAQs visible in HTML, breadcrumbs, towns served as links, NAP with hours and license, local proof, schema subtype, review recency, and so on).

## Step 2: build the template

Follow `TEMPLATE_BRIEF.md` (same folder) exactly for the file format, the copy rules and the required sections, with these overrides:
- Page length 9–12 sections, about 3,500–5,000 px tall at 1280 wide. Set `$preview` height to your estimate rounded up to the next 100.
- Borrow the source's STRUCTURE, CONVERSION MECHANICS and DESIGN-SYSTEM LANGUAGE (layout patterns, type classification, element shapes, density, badge, coupon and card styles, color roles). It should feel like a sibling of the source site.
- Never copy its BRAND: no brand or franchise names, logos, mascots, slogans or taglines, trademarked program names (like "a franchise group Done Right Promise"), photos, or the same signature color combination. Pick an original palette that keeps the same color roles and contrast structure but uses a different main hue. Pick Google Fonts in the same type classification (for example, a condensed grotesk for a condensed grotesk); do not use the source's own font if it is a custom or brand typeface.
- Fix the SEO gaps you found, visibly, in the page.
- Sample business: a fictional single-location contractor. You choose its name. It must not echo the source brand's name or wordplay, and it must not reuse these earlier sample names: Bayline, Coolwater, Sandhill, Brightline, Greenline, Rivera, Tidewell, Keystone, Hollis & Pine, Meridian, Palmetto, Clearday, Northstar, Plumbline. Use the city and phone assigned to you below.
- Give the template a short descriptive variant name of 2–3 words that does not use the source brand (for example "Coupon Wall", "Truck-Side Trust", "Neighborhood Ledger").
- Add one small visible line at the very bottom of the footer, in muted text: `Avenue Vision template V__ · [variant name]`.

Write each file with your file-writing tool to:
`/tmp/claude-0/-home-claude/79cb5c0e-ffb6-51d2-8a76-be73d1c9c066/scratchpad/bv/project/<FILENAME>`
Do not edit any other file. Do not publish.

## Step 3: check

Re-read each file once and check: every tag closed; attributes quoted; no CSS outside inline style attributes except the helmet's body-margin rule; no `<img>`; no emoji; no exclamation marks; no sc-for or sc-if inside tables; data-props JSON valid with no single quotes; the support.js line present; no brand names from the source. If Python and Playwright are available (`python3 -c "import playwright"`), render the file at 1280 wide and at 390 wide (strip the support.js line and the trailing text/x-dc script first). Confirm nothing scrolls sideways at 390, and set `$preview` height to the measured 1280 height rounded up to the next 100.

## Reply (under 180 words per template)

For each template give:
- the filename;
- the variant name;
- the source studied and the URLs you fetched;
- 3 bullets on what you borrowed (structure, mechanics, design language);
- 3 bullets on the SEO and CRO gaps you fixed;
- the fonts and palette;
- the final `$preview` height.
