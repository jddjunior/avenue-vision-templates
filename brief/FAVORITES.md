# Round 3 brief: more like the client's favorites (D11, D13, D14)

Follow `DIRECTIONS.md` in this folder exactly: its process, file format, SEO checklist, photo rules and the critique round. This file adds the target and the overrides.

## The client's three favorites

Look at all three full-page renders first:
- `/tmp/claude-0/-home-claude/79cb5c0e-ffb6-51d2-8a76-be73d1c9c066/scratchpad/shots/D13-full.png` — Poster Stack (pressure washing). Full-bleed flat-color sections, each one its own poster. Huge friendly type, Bauhaus shapes, a floating pill nav, services as a stack of link pills, and photos set in arch and circle frames.
- `/tmp/claude-0/-home-claude/79cb5c0e-ffb6-51d2-8a76-be73d1c9c066/scratchpad/shots/D14-full.png` — Retro Soda Shop (handyman). Cream and teal, a soft retro serif, pastel "flavor" cards with round photos, a checkerboard, a menu-board price list, a nutrition-label "Shop Facts" panel and a bottle-cap rating.
- `/tmp/claude-0/-home-claude/79cb5c0e-ffb6-51d2-8a76-be73d1c9c066/scratchpad/shots/D11-full.png` — Friendly Fintech (AC replacement). A chat-style instant quote, big friendly numbers, very round cards, coral on mint, rotated enamel-pin badges, a hand-drawn map and FAQs as chat bubbles.

What they share, and what to hit:
1. **A consumer brand, not a contractor template.** Each feels like a direct-to-consumer brand that people would follow (a soda, a bank, a poster series), applied to a home-service business.
2. **Confident color with personality and warmth.** Bold, joyful and friendly. Never corporate, dark-luxury or grey.
3. **Content turned into branded objects.** Each one makes a required block into a playful object: prices become a menu board, business details a nutrition label, the FAQ chat bubbles, services link pills, the rating a bottle cap. Every page you build needs at least 3 such objects, and they must be new ones (do not reuse menu board, nutrition label, chat-bubble FAQ, bottle cap or link pills).
4. **Photos given shape.** Arches, circles, stickers, tilted frames, cutouts, rounded tiles.
5. **Illustration and badges.** Inline SVG shapes, badges, seals, simple drawn icons and maps. A mascot is fine if it is original and simple (geometric, not a copy of any known character).
6. **A warm, plain, slightly witty voice**, still truthful and specific, with no exclamation marks.

Each new page must be clearly its own direction. Do not make a copy of D11, D13 or D14. It should feel like it belongs in the same family, the way different DTC brands do.

## Overrides

- **Height:** the canvas cuts boards off at 8,000 px. Keep every page at 7,800 px or less tall at 1280 wide (measured). Aim for 5,000–7,000.
- **Photos:** new pools exist for `poolsvc`, `paint`, `fence`, `moving`, `carpet`, `solar`, `appliance` and `gdoor`. Older pools such as `plumb`, `elec`, `pest` and `clean` are still there. Contact sheets: `/tmp/claude-0/-home-claude/79cb5c0e-ffb6-51d2-8a76-be73d1c9c066/scratchpad/photosheets/<trade>.jpg`. Note that `solar/03.jpg` does not exist.
- **Footer line:** `Avenue Vision · E__ · [direction name] · style refs withheld`.
- **File names:** `E01.dc.html` … `E12.dc.html`. Prefix every CSS class with the file id, e.g. `.e05-hero`.
