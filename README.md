# eCommerce Georgia 2026 — website

```
site/                     ← this folder is what gets published (GitHub Pages)
  index.html              the live page: sponsors / partners (packages, pricing)
  assets/img/v26/         assets exported from "Web Visual 2026 _Folder"
  assets/img/             older assets from the deck (event photos, partner walls, logo, icons)

hidden/                   ← NOT published — kept outside site/ on purpose
  attendee-page.html      attendee page built from the designer's mockup (speakers, demos, tickets)
```

HTML, CSS and JS are inline — no build step. Upload the contents of `site/` to the host.
Locally, from the project root: `python3 serve.py`, then open <http://127.0.0.1:4321>.
The hidden page can be opened straight from disk: `hidden/attendee-page.html`.

## Bringing the attendee page back (once speakers, demos and tickets are ready)

1. Move `hidden/attendee-page.html` into `site/` and change every `../site/assets/` in it back to `assets/`.
2. Decide which page is the front door. The attendee page was designed as the main page, so the usual
   move is: rename the current `site/index.html` to `site/sponsors.html`, and the attendee page to
   `site/index.html`.
3. Re-add the cross-links: the attendee footer links to `sponsors.html`
   ("Partnership packages →"); the sponsors footer had "Attending? Visit the event page →" to `index.html`.

The design-system notes below describe the attendee page.

## Design system (from the mockup)

| | |
|---|---|
| Type | Montserrat — 400 / 500 / 600i / 700, 300 italic for "2026" |
| Page background | `#EDEDED`, white cards, text `#232323` |
| Coral | `#FF6D58` (titles, buttons), `#FF7861` (icons, hero date) |
| Dark cards | plum gradients from `#8B4A71` to `#130A21`, running left to right across each row |
| Scale | The mockup is a 1920px artboard. Most `clamp()` maxima are its px values, so the page matches it at 1920 and scales down proportionally |

## Assets in `assets/img/v26/`

| File | Source |
|---|---|
| `cart.webp`, `cart-900.webp` | `Links/Motion Bluer .psd`, trimmed, transparent |
| `hero-bg.webp` (+ `.jpg`, `-1200.webp`) | `Backgrounds/Web Visual 2026 -02.png` |
| `footer-bg.webp` | `Backgrounds/Web Visual 2026 -05.png` |
| `icon-cart.svg`, `icon-growth.svg`, `icon-crossborder.svg` | `ICONS SVG/Asset 2, 1, 3` |
| `speaker-1…5.jpg` | Photo crops of the earlier deck speaker cards |
| `og.jpg` | Hero background + cart composite for social sharing (1200×630) |

Backgrounds `-03` / `-04` (gradient card fills) are rebuilt in CSS instead of used as images.

## Content still needed before launch

- **Ticket link.** Every Tickets button uses `TICKETS_URL` at the top of the `<script>`. It is a
  `mailto:info@ecag.ge` placeholder for now.
- **2026 speakers.** The Speakers section shows 5 speakers from previous editions and says so.
  The mockup's cards were placeholders. Partner logos from the mockup (Google Cloud, Avianca,
  Melo, Amadeus…) were not in the designer's package, so company names are set as text.
- **Panel discussions.** 3 "to be announced" cards.
- **Demo Live.** No presenter names or video links. The play icons are decorative. In the mockup,
  the Storera and CityPay.io/Tether logos were paired with each other's titles. The page pairs each
  title with its own company.
- **Mockup copy that was out of date.** The mockup said "third edition" and "eCommerce Day 2025 …
  October 31". The page says fourth edition, 6 November 2026. Please confirm the edition number.
- **Stats.** The page uses the mockup's numbers: 1200+ / 30+ / 50+ / 20+. The earlier deck said
  1500+ attendees / 60+ speakers.
- **Contact.** The footer uses `info@ecag.ge`, as in the mockup. `sponsors.html` still uses `egadzek@ecag.ge`.
