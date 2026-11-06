# Sale Listing

## Single-file Verve restaurant website demo — Bukhara

Verve is a responsive, single-file restaurant front end for a Bukhara fast-casual concept, with Uzbek, English, and Russian interfaces. It includes a 12-item menu, local demo ordering and rewards flows, and a browser-only owner dashboard, plus optional Python Telegram bot/local order-bridge code. It is a ready-made prototype rather than production commerce; the buyer must verify claims and image rights and add secure backend, payment, and deployment services before taking real orders.

## Features in the supplied code

- One self-contained HTML page with inline CSS and JavaScript; no front-end build step.
- Twelve menu items with categories, search, category/diet filters, sorting, item customization, and a combo builder.
- Cart with built-in promotions, demo reward redemption, delivery/pickup/table-reservation modes, and a local checkout/order-status flow.
- Uzbek, English, and Russian language switching, plus light/dark themes.
- Browser-local owner dashboard for menu prices/descriptions/availability, opening hours, delivery settings, and promotion controls.
- First-use owner password setup that stores a salted PBKDF2-SHA256 hash in the browser.
- Local review submission and category summaries, plus local rewards profiles.
- Optional `script2.py` Telegram bot and loopback HTTP service for Telegram bot orders; its token is read from `TELEGRAM_BOT_TOKEN`.

These are demo features. Browser data is editable and not shared, and the website checkout does not use a production backend.

## Not included

- A production backend, database, authenticated admin API, secure multi-user sessions, order validation, rate limiting, or real payment processing.
- A domain, hosting account, deployment, business operations, delivery fleet, customer list, sales history, revenue, or analytics.
- Bot credentials, payment-provider credentials, or seller accounts.
- Image files or verified/transferable rights to the hotlinked Unsplash/Pexels images.
- Confirmed restaurant contact details, hours, menu prices, promotions, rewards terms, or substantiation for marketing claims.
- The original `endofproject.html` comparison copy; it contains retired seller-specific details and must not be transferred.

## Price rationale

For planning only, a buyer might avoid approximately **25–40 engineering hours** of recreating a comparable front-end prototype and local demo flows. This is a rough scope estimate, not a timesheet, independent valuation, guaranteed saving, or estimate of production-backend work. No asking price is stated because no verified traffic, revenue, customer base, domain, operating costs, or market valuation was supplied; the buyer should price the asset accordingly and budget separately for productionization.

## FAQ

**Can I take real paid orders immediately?**  
No. The website stores demo state in the browser, and the bot's online-payment choice is not a payment integration. See [LIMITATIONS.md](./LIMITATIONS.md).

**Can I edit menu prices and hours?**  
Yes, through the browser-local dashboard or the source defaults. Dashboard edits do not automatically publish to other browsers or devices.

**Are the photos included or cleared for transfer?**  
No. They are hotlinked. The license review and individual source URLs are in [HANDOVER.md](./HANDOVER.md); the buyer should verify or replace them.

**What do I need to run the Telegram bot?**  
A buyer-issued Telegram bot token in `TELEGRAM_BOT_TOKEN`, Python, and a compatible `aiogram` installation. The files do not include a pinned dependency manifest or a hosted deployment.

**Does the sale include the original source copy or an existing owner password?**  
No. Transfer only the final `telegramm.html`, `script2.py`, and agreed handover documents. The buyer sets a new owner password in their own browser.
