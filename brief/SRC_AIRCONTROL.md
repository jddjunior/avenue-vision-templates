# Round 4 brief: five templates from the [study site] source

Read this file first. It holds the study, the shared rules, and one spec per template (H01 to H05). Also follow `TEMPLATE_BRIEF.md` in this folder, except where this file overrides it.

## 1. What the source does (studied: homepage and the Kingman location page)

Homepage, top to bottom: a promo bar (financing, with a link to apply), a header (phone, a Book Online button, a mobile menu), a hero (a "Since 1990" tagline, a Book Online button and an H1 that names HVAC, electrical and plumbing across three towns), four trade cards (Heating, Cooling, Plumbing, Electrical, each with a one-line pitch and a "View Service" link), an owner-story block, a video, alternating trade blocks with photos, a trust logo strip, a reviews heading with no visible rating, a membership plan card with four icon benefit cards, a map, a service-area town list, a footer with three office addresses and license numbers, and a five-step booking modal.

Kingman location page: a breadcrumb (Home / Kingman, AZ), an H1 "Plumbing, HVAC & Electrical Services in Kingman, AZ", a "Request a Visit" button, H2s of the form "[Service] in Kingman, AZ" with H3 subsections, service links with city slugs (for example /ac-repair-kingman-az/), a named financing lender, a "Don't miss out" specials line, guarantees stated as numbers (1-year labor warranty, 100% satisfaction guarantee), the membership cards, a reviews heading with no rating, the town list, FAQ-style H2 blocks and a repeated booking form.

## 2. What we borrow (structure and mechanics)

1. A promo or financing bar above the header, with a link and a qualifier in small print.
2. A header that always shows the phone and one booking button.
3. A multi-trade hero: a city-first H1, a heritage line ("Since [YEAR]") and one primary action.
4. Four trade cards (Heating, Cooling, Plumbing, Electrical), each with a one-line pitch and a link to its own service page, with the slug shown.
5. A membership plan card: a monthly price, four benefits with icons, and a details link.
6. Guarantees stated as numbers.
7. A short booking form (our version is an inline 3-step form, not a modal).
8. A service-area list of towns, all linked, with a map-like panel.
9. A footer with NAP, license line and hours.

## 3. Design language we can confirm, and what we cannot

Confirmed: one set of line icons; a trust-logo strip in a single row; wide photos of real crews and job sites; cards built from icon or image, title and one line; section heads with a divider underneath; a long keyword H1 (we shorten it); Title Case button labels.

Not confirmed: hex colours, typefaces, button shape, shadows and heading scale (the capture has no CSS). So every template picks its own palette and fonts. Do not say or imply that any template matches the source's colours or type.

## 4. SEO and CRO gaps to fix in every template

- No price ranges on the source: add `$[LOW]–$[HIGH]` ranges.
- No FAQs in the HTML: four FAQs, answers visible.
- No hours: `[HOURS]` in the footer and near the booking form.
- No visible schema: NAP and license in the footer, written as text.
- Only two towns are linked, and the main market is not linked: list six or more towns, all linked as `/areas/<town>`.
- Reviews heading with no rating: "[RATING] from [COUNT] Google reviews" and a recency line "Newest review [DAYS] days ago".
- Duplicate booking forms and duplicate FAQ headings: one form, one FAQ.
- Malformed `www.www.` links: none. Every link is clean.
- Empty alt text on most images: every image gets a descriptive alt.
- A long keyword H1 that dilutes focus: one H1 with the city and the main service.

## 5. Shared rules (these override TEMPLATE_BRIEF.md)

- Photos: use REAL photos from `bv/project/img/<trade>/NN.jpg`, not grey placeholders. Look at the labelled contact sheet `photosheets/<trade>.jpg` first. Use the photos allocated to your template below. Use `<img src="img/<trade>/NN.jpg" alt="…" width="…" height="…" style="object-fit: cover; …">` with a relative src. The hero image gets no `loading` attribute; the others get `loading="lazy"`. Every image gets a descriptive alt. Reuse of a photo across templates is allowed if the crop differs.
- Styles: one Google Fonts `css2` link and ONE `<style>` block in `<helmet>`. Real CSS is allowed there. Prefix every class with your file id (`.h01-hero`, `.h02-card`, …). Keep `body{margin:0}`. Inline styles are fine too.
- Skeleton: copy the `<head>`, `<x-dc>`, `<helmet>`, root div and trailing `text/x-dc` script exactly as they appear in `bv/project/E01.dc.html`. Read its first 12 lines and last 8 lines first. Keep `<script src="./support.js"></script>` in the head.
- No `<sc-if>`, no `<sc-for>`, no `<iframe>`, no JS libraries, no external images. Write every repeated block out literally.
- Fictional businesses only, with the name, city and phone given in your spec. Never use an HVAC franchise, its phone numbers, its addresses, its ROC licence numbers, its tagline, its "Comfort Club" name or any of its wording. Do not reuse these earlier names: Bayline, Coolwater, Sandhill, Brightline, Greenline, Rivera, Tidewell, Keystone, Hollis & Pine, Meridian, Palmetto, Clearday, Northstar, Plumbline, Bayshore, Orla, Coquina, Paddock, Hogtown, Breezly, Turfstat, Saltline, Canopy Road, Palafox, Cannonball, Bellini, Cherry Top, Haulsome, Softspot, Heydoor, Bitewise, Blue Plate, Good Sparks, Tidy Citrus, Marsh & Pine, Nothing Left, Brick Street, Fourth Street, Bayshore.
- Copy rules (TEMPLATE_BRIEF section 2): plain and confident, written like a local tech talking at the door; "we" and "you"; no exclamation marks; no emoji; no "Welcome"; no "best-in-class". Button labels are two or three word Title Case verbs ("Book Online", "Call (480) 555-0141", "Get My Price", "Request a Visit"). Never "Submit", "Learn More" or "Click Here". Phones are written `(480) 555-01xx` and linked with `tel:+1480555…`.
- Every fact the owner must supply stays in brackets: `[LICENSE NO.]`, `[YEARS]`, `[YEAR]`, `[PRICE]`, `[LOW]`, `[HIGH]`, `[RATING]`, `[COUNT]`, `[DAYS]`, `[HOURS]`, `[STREET ADDRESS]`, `[ZIP]`, `[OWNER NAME]`, `[WARRANTY YEARS]`, `[CERTIFICATION]`.
- Offers carry a qualifier and an expiry in small print: "With completed repair. One per household. Expires 12/31/2026."
- Reviews: NEVER invent a testimonial in a person's voice. Use stars drawn as inline SVG, the text `[Google review, pulled at build time]`, attribution `[Reviewer], [Town]`, and a recency line.
- Contrast: text at least 4.5:1 (3:1 for 24 px and up). Buttons and tap targets at least 44 px tall. Check the text colour on every CTA.
- Length: 9 to 13 sections, measured height 4,000 to 6,000 px at 1280 wide. Never above 7,800 px (the canvas cuts boards off at 8,000).
- Width: works at 390 px with no sideways scroll. Use `grid-template-columns: repeat(auto-fit, minmax(min(260px, 100%), 1fr))` for card rows.
- Footer muted line, last thing on the page: `Avenue Vision · H0X · [direction name] · studied: [study site] homepage and Kingman page`.

## 6. The shared section list (every template has all of these, each skinned differently)

1. Promo or financing bar with a qualifier and expiry.
2. Header: an inline SVG logo mark plus wordmark, at most six nav items, the phone as a tel link, one primary button.
3. Hero: city-first H1 ("[City] Heating, Cooling, Plumbing & Electrical"), one primary action, an evidence line "[RATING] from [COUNT] Google reviews".
4. Trust row: licensed, insured, `[WARRANTY YEARS]`-year labor warranty, 100% satisfaction guarantee, "Since [YEAR]".
5. Four trade cards: Heating, Cooling, Plumbing, Electrical. Each has a slug link such as `/furnace-repair-[city]`, a one-line pitch and a price range.
6. The signature section (given in your spec).
7. Membership plan card (the name is in your spec): `$[PRICE]/month`, four benefits with icons, a details link.
8. Reviews: stars, placeholder quote, reviewer and town, recency line.
9. Service area: six or more towns, all linked as `/areas/<town>`, plus a ZIP checker input with a button.
10. FAQ: four questions phrased the way people search, answers visible in the HTML.
11. Booking: one inline 3-step form (service, preferred day, name and phone), with a Title Case button.
12. Footer NAP: business name, `[STREET ADDRESS], [City], AZ [ZIP]` (or "Service area business"), phone, `[HOURS]`, `[LICENSE NO.]`, the towns served, service links, legal line, and the muted footer line.

## 7. Per-template specs

### H01 · Ledger Utility · Mesa
- Business: Saguaro Comfort Co. Phone (480) 555-0141. City: Mesa.
- Palette: navy #14213D for the header, footer and dark bands; cream #F5F0E6 ground; signal orange #E8571E for CTAs with navy text; ink #14213D.
- Fonts: Barlow Condensed (700, 800) for headings; Barlow (400, 500, 600) for body.
- Photos: `ac/02`, `ac/06`, `ac/09`, `plumb/01`, `elec/01`.
- Signature moves: (1) a "Your bill" price ledger: a receipt-style table of service ranges `$[LOW]–$[HIGH]` with dotted leaders; (2) numbered service rows, each with its slug; (3) an orange promo bar with a small-print qualifier.
- Membership name: "Keep Cool Plan".
- Neighbouring towns: Gilbert, Tempe, Apache Junction, Queen Creek, Chandler, Scottsdale.

### H02 · Desert Sunrise · Gilbert
- Business: Ocotillo Heat & Air. Phone (480) 555-0162. City: Gilbert.
- Palette: sand #F7EDE2 ground; ink #3A2A22 for text and dark bands; terracotta #B4462A for CTAs with white text (check the contrast); sage #5C7A5E for secondary accents.
- Fonts: Big Shoulders Display (700, 900) for headings; Source Sans 3 (400, 600, 700) for body.
- Photos: `ac/03`, `ac/05`, `ac/08`, `wh/01`.
- Signature moves: (1) arched photo frames (rounded top, `border-radius` on the top corners only) for the hero and the service cards; (2) a sun-arc "Since [YEAR]" badge; (3) the membership as a perforated ticket with a dashed tear line.
- Membership name: "Cool Season Plan".
- Neighbouring towns: Mesa, Chandler, Queen Creek, San Tan Valley, Higley, Tempe.

### H03 · Membership Card · Chandler
- Business: Mesquite Mechanical Co. Phone (480) 555-0183. City: Chandler.
- Palette: deep teal #0E5E63 for the hero band; cream #FBF8F1 ground; gold #E2A92B for CTAs with #12303A text; ink #12303A.
- Fonts: DM Serif Display (400) for headings; DM Sans (400, 500, 700) for body.
- Photos: `ac/07`, `plumb/02`, `elec/03`, `wh/02`.
- Signature moves: (1) the membership as the hero object: a card-shaped panel with `[MEMBER NAME]`, the plan name, `$[PRICE]/month` and the first three benefits; (2) a three-tier plan comparison (Basic, Plus, Premium), with brackets on every price; (3) the trust row as round stamped seals.
- Membership name: "Home Care Plan".
- Neighbouring towns: Gilbert, Tempe, Ahwatukee, Sun Lakes, Mesa, Queen Creek.

### H04 · Field Notes · Peoria
- Business: Red Mesa Air & Electric. Phone (623) 555-0124. City: Peoria.
- Palette: paper #F3EFE4 ground; ink #1E2A32; stamp red #B23A2E for CTAs with white text; carbon blue #2D4F7C for links and accents.
- Fonts: IBM Plex Sans Condensed (600, 700) for headings; IBM Plex Sans (400, 500) for body; IBM Plex Mono (400, 500) for slugs, numbers and labels.
- Photos: `ac/01`, `ac/04`, `elec/02`, `plumb/03`.
- Signature moves: (1) the hero is a job ticket: a real HTML form with fields for name, address, service type (a select) and preferred window, and a "Book Online" button; (2) the services as numbered field-guide entries, each with a "Common fix" line and a price range; (3) the specials as a rubber-stamp coupon with a qualifier and an expiry.
- Membership name: "Maintenance Plan".
- Neighbouring towns: Glendale, Surprise, Sun City, El Mirage, Sun City West, Litchfield Park.

### H05 · Route Map · Tucson
- Business: Catalina Cool Co. Phone (520) 555-0197. City: Tucson.
- Palette: slate #1B2A2F for the header and hero band; light ground #EEF2EF; lime #C6F432 for CTAs with #1B2A2F text; route teal #2F7F78 for lines and accents.
- Fonts: Space Grotesk (500, 700) for headings; Inter (400, 500, 600) for body.
- Photos: `ac/09`, `wh/03`, `plumb/04`, `elec/04`.
- Signature moves: (1) an inline-SVG service-area map in the hero, with a street grid and town pins; each pin is a link to `/areas/<town>`; (2) a "Next openings" dispatch strip with `[DATE] [TIME]` placeholders and no invented availability; (3) the service cards laid out as route stops, each with its slug.
- Membership name: "Route Care Plan".
- Neighbouring towns: Marana, Oro Valley, Sahuarita, Vail, Catalina, South Tucson.
