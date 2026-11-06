# Verve Website Handover

## What is included

- `telegramm.html` — the complete single-file website. Its CSS and JavaScript are inline; there is no build step or separate front-end asset bundle.
- `script2.py` — the optional Telegram bot and loopback HTTP order server. It reads `TELEGRAM_BOT_TOKEN` from the process environment; no bot token is included.
- `LIMITATIONS.md`, `LISTING.md`, and `TRANSFER_CHECKLIST.md` — buyer-facing scope, risk, and transfer notes.

Do not include `endofproject.html` in the sale package. It is the unmodified comparison copy and still contains the retired demo password and owner-specific contact information. The customer phone shown as `+998 90 123 45 67` in the final HTML is an input example, not the restaurant's phone number.

## How to run

### Website-only demo

Open `telegramm.html` in a modern browser. Menu browsing, theme/language switching, the cart, promotions, demo checkout, reviews, rewards, and owner dashboard store their state in that browser.

### Optional Telegram bot and local order server

`script2.py` requires Python and the `aiogram` package. No pinned dependency manifest was present with the supplied files, so the buyer should choose and test a compatible `aiogram` version in a virtual environment.

From the folder containing `script2.py` and `telegramm.html`, in PowerShell:

```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
python -m pip install aiogram
$env:TELEGRAM_BOT_TOKEN = "<token issued for the buyer's bot>"
# Optional; defaults to 8765:
$env:VERVE_WEB_PORT = "8765"
python script2.py
```

The script starts Telegram polling and a web server bound to `127.0.0.1`. With the default port, the website is served at `http://127.0.0.1:8765/`. The token must be issued/rotated for the buyer and supplied through the environment; never put it in the HTML, Python file, or a public repository. The web server is a local demo service, not a public hosting setup.

The browser website's demo checkout saves to browser storage; it does not submit its checkout to this server. The server endpoints currently serve the website and exchange Telegram bot orders.

## Where to make common changes

All website edits below are in `telegramm.html`:

- **Menu content/default prices:** find the `MENU` array. The owner dashboard can override prices, descriptions, and availability, but those edits live in that browser's `localStorage`; update the source defaults for a buyer-facing copy.
- **Item sale percentages:** find `ITEM_DISCOUNTS`. These percentages are used to calculate the displayed sale prices.
- **Menu and hero images:** find `FOOD_PHOTOS` and the image `src` attributes in the page markup. These currently point to external image CDNs; see the asset inventory below.
- **Hours, delivery fee/threshold, and estimated delivery time:** find `DEFAULTS` (`open`, `close`, `deliveryFee`, `freeThreshold`, `etaMin`, `etaMax`). The dashboard can edit these values locally, but does not publish them to other browsers.
- **Built-in promotions:** find `PROMOS`. The dashboard can turn these on/off and add browser-local custom percentage promotions.
- **Languages:** the language selector uses `uz`, `en`, and `ru`. Find the `translations` dictionaries and `data-i18n` markup. When adding text, add translations for all three languages; dictionary lookup normalizes whitespace, so line wrapping in source text does not need to match exactly.
- **Brand colors and themes:** find the inline `<style>` block's `:root` color variables (including `--p-gold` and `--accent`) and the light-theme overrides.
- **Restaurant address, phone, and directions:** replace the clearly marked `[OWNER: ...]` placeholders in the visit section, and update the corresponding contact text in `script2.py`'s `UI_TEXT` language dictionaries. The bot's business hours and rewards wording are also marked for owner confirmation.

Changing local dashboard values is not a substitute for changing authoritative server data before launch. See [LIMITATIONS.md](./LIMITATIONS.md).

## External asset and licensing inventory

The HTML hotlinks to 16 unique Unsplash photo IDs and one Pexels photo. Some Unsplash IDs are requested more than once at different sizes/quality settings; the URLs below identify each distinct photo source.

### Unsplash photos

Source/license reference: [Unsplash License](https://unsplash.com/license). The live license page could not be retrieved during this handover review, and no per-photo source pages or license records were provided. Commercial-use permission for the buyer is therefore **not confirmed here**; do not represent that image rights transfer with the website. The buyer should verify the current license and the exact images, or replace them with buyer-owned/licensed images.

- [`photo-1594212699903-ec8a3eca50f5`](https://images.unsplash.com/photo-1594212699903-ec8a3eca50f5?auto=format&fit=crop&w=1400&q=92) — also used at other widths.
- [`photo-1626700051175-6818013e1d4f`](https://images.unsplash.com/photo-1626700051175-6818013e1d4f?auto=format&fit=crop&w=1400&q=92) — also used at other widths and with a saturation parameter.
- [`photo-1547592180-85f173990554`](https://images.unsplash.com/photo-1547592180-85f173990554?auto=format&fit=crop&w=700&q=88)
- [`photo-1517248135467-4c7edcad34c4`](https://images.unsplash.com/photo-1517248135467-4c7edcad34c4?auto=format&fit=crop&w=700&q=88)
- [`photo-1515003197210-e0cd71810b5f`](https://images.unsplash.com/photo-1515003197210-e0cd71810b5f?auto=format&fit=crop&w=700&q=88)
- [`photo-1568901346375-23c9450c58cd`](https://images.unsplash.com/photo-1568901346375-23c9450c58cd?auto=format&fit=crop&w=900&q=88)
- [`photo-1550547660-d9450f859349`](https://images.unsplash.com/photo-1550547660-d9450f859349?auto=format&fit=crop&w=900&q=88)
- [`photo-1573080496219-bb080dd4f877`](https://images.unsplash.com/photo-1573080496219-bb080dd4f877?auto=format&fit=crop&w=900&q=88)
- [`photo-1630384060421-cb20d0e0649d`](https://images.unsplash.com/photo-1630384060421-cb20d0e0649d?auto=format&fit=crop&w=900&q=88)
- [`photo-1562967916-eb82221dfb92`](https://images.unsplash.com/photo-1562967916-eb82221dfb92?auto=format&fit=crop&w=900&q=88)
- [`photo-1554866585-cd94860890b7`](https://images.unsplash.com/photo-1554866585-cd94860890b7?auto=format&fit=crop&w=900&q=88)
- [`photo-1544145945-f90425340c7e`](https://images.unsplash.com/photo-1544145945-f90425340c7e?auto=format&fit=crop&w=900&q=88)
- [`photo-1565299507177-b0ac66763828`](https://images.unsplash.com/photo-1565299507177-b0ac66763828?auto=format&fit=crop&w=900&q=88)
- [`photo-1585109649139-366815a0d713`](https://images.unsplash.com/photo-1585109649139-366815a0d713?auto=format&fit=crop&w=900&q=88)
- [`photo-1562967914-608f82629710`](https://images.unsplash.com/photo-1562967914-608f82629710?auto=format&fit=crop&w=900&q=88)
- [`photo-1577805947697-89e18249d767`](https://images.unsplash.com/photo-1577805947697-89e18249d767?auto=format&fit=crop&w=900&q=88)

### Pexels photo

- [`photo-96974`](https://images.pexels.com/photos/96974/pexels-photo-96974.jpeg?auto=compress&cs=tinysrgb&w=1400) — Pexels' [license page](https://www.pexels.com/license/) says photos and videos may be used online, including on websites and e-commerce shops. Commercial online use is generally permitted under that license, subject to its terms. The exact photo/source page was not identified in the supplied code, and the image is hotlinked rather than included; verify the particular asset and current terms before representing transfer rights.

The footer also links to the generic [Pexels website](https://www.pexels.com/). No external fonts, icon libraries, or JavaScript libraries were found; fonts use system stacks and icons are inline SVG. No external map link remains in the final page.

**Hotlink risk:** remote images can change, disappear, or be served under terms that do not cover the buyer. Replace them with images the buyer owns or has documented rights to use. If the single-file constraint remains, approved images can be embedded as data URLs; otherwise use a buyer-controlled image host.

## Claims requiring owner confirmation

No evidence documents the business claims below. Confirm or remove each before public launch:

- All menu prices, crossed-out/original prices, and item discount percentages.
- The default built-in offers `WELCOME10`, `YARIM50`, `COMBO25`, and `1PLUS1`, plus any custom offer terms.
- The rewards terms (1 point per 1,000 UZS and 5,000 UZS off for 100 points), eligibility, exclusions, and redemption rules.
- The default hours (10:00–23:00), delivery fee (12,000 UZS), free-delivery threshold (150,000 UZS), delivery estimate (25–35 minutes), and pickup estimate (15–20 minutes).
- “HALAL FRIENDLY,” “FRESH DAILY,” and “MADE IN BUKHARA,” as well as “Bestseller” and “Feed two.”
- Any review/rating shown as customer evidence. Reviews are submitted and stored in the browser; this code does not verify identities or external review sources.
- The 2026 copyright year and the bot's promise that an operator will contact the customer.
- The restaurant address, phone, directions link, and contact/hours/rewards wording in the bot; these are intentionally placeholders pending owner input.

No “since [year]” claim was found in the final page.

## Verified behavior and intentional differences

The final page was loaded in a headless browser in Uzbek, English, and Russian. In each language, 12 menu cards rendered. The browser checks also exercised theme switching, cart addition, `WELCOME10`, checkout to a local accepted demo order, first-run owner-password setup, rejection of a short/mismatched password, hash-only PBKDF2 storage, and subsequent owner login. No browser console errors or page errors were observed. Desktop and mobile computed-style comparisons found no substantive visual regression; changed content height reflects replaced contact details, and the corrected `html, body` transition now includes the intended border-color transition.

The original `endofproject.html` comparison page also rendered 12 items in each language and its local cart/promo/checkout flow completed. It is not the sale deliverable and is intentionally not sanitized or included.

Intentional customer-visible/code differences from the old copy:

- The old owner phone, neighborhood, and map location were replaced with owner placeholders in the final website and bot copy.
- The old hard-coded demo password was removed. The first owner login now requires a password of at least 10 characters and stores a salted PBKDF2-SHA256 hash in browser storage.
- Russian and Uzbek owner-password/contact placeholders were corrected; whitespace is normalized during translation lookup.
- Styles/scripts were consolidated, malformed CSS was repaired, true duplicate button rules were removed, and `!important` declarations were removed. Scoped responsive button overrides remain because they serve different layouts. The tested layout remained visually consistent.
- `script2.py` now serves `telegramm.html` from its own directory, uses the correct `/telegramm.html` route, and has owner contact/hours/rewards placeholders.

The browser tests used dummy local data and did not connect to Telegram, a live payment provider, or a production backend. `script2.py` was syntax-checked, not run with a real bot token. See [LIMITATIONS.md](./LIMITATIONS.md).
