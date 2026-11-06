# Sale-Day Transfer Checklist

## Before handing over files

- [ ] Agree in writing on the exact assets being sold: `telegramm.html`, `script2.py`, and the agreed handover documents.
- [ ] Exclude `endofproject.html`; it is the old comparison copy and still contains seller-specific details and the retired demo password.
- [ ] Do not include `.env` files, bot tokens, payment credentials, browser profiles, local storage exports, customer orders, or `telegram_orders.json`.
- [ ] Tell the buyer that the Unsplash/Pexels photos are hotlinked and that image rights must be independently verified or the images replaced.
- [ ] Provide the buyer with the known limitations in `LIMITATIONS.md`; do not describe the demo as production-ready.

## Seller account and key cleanup

- [ ] Remove the seller's token from the seller's environment, deployment settings, shell profiles, and any private notes or backups that will not transfer.
- [ ] Revoke/rotate the seller's Telegram bot token and any other credentials that were used for this project. The delivered `script2.py` reads a buyer token from `TELEGRAM_BOT_TOKEN`; it does not contain one.
- [ ] Remove the seller's personal accounts and access from any bot, hosting, domain, image, analytics, or payment services involved. No such accounts are included in these files.
- [ ] Keep or dispose of seller-side source copies and browser-local test data according to the seller's own retention policy; do not pass them to the buyer unless explicitly agreed.

## Buyer setup

- [ ] Buyer confirms receipt and checks that the final file opens and that all contact placeholders are visible.
- [ ] Buyer sets a new owner password (at least 10 characters) on the buyer-controlled browser. Do not transfer a seller password or copy the seller's `localStorage`.
- [ ] Buyer replaces the business address, phone, directions, hours, and bot contact/reward text in the marked locations.
- [ ] Buyer verifies menu prices, discounts, promotion terms, delivery fees/thresholds, estimates, rewards, and marketing claims.
- [ ] Buyer verifies or replaces every external image with buyer-owned or otherwise documented licensed images.
- [ ] If the bot is required, buyer issues their own Telegram token, sets `TELEGRAM_BOT_TOKEN`, installs and pins a compatible `aiogram` dependency in their environment, and tests locally.
- [ ] Buyer does not expose the loopback order service publicly. Production use requires the backend, authentication, validation, payment, privacy, and deployment work described in `LIMITATIONS.md`.

## Written confirmation

- [ ] Both parties confirm the exact filenames and version received.
- [ ] Both parties list any included/excluded brand, image, account, domain, customer-data, or intellectual-property rights; do not assume rights that were not documented.
- [ ] Both parties confirm that the delivered website and bot are demo code and that no live customer data, sales, revenue, payment integration, or production hosting is represented as included.
- [ ] Seller records that seller credentials were revoked/rotated and buyer records that buyer credentials/password were set independently.
