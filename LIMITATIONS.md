# Known Limitations

This is a polished prototype, not a production restaurant-commerce system.

## Browser-only state is not secure or shared

- Owner login, menu-price/description/availability edits, hours and delivery settings, promo configuration, rewards profiles, reviews, cart, and the HTML checkout's orders are stored in browser `localStorage`.
- The owner password is set on first use and stored as a salted PBKDF2-SHA256 hash, not plaintext. That is still only a browser-local gate: a user who controls the browser can change its code or storage, clear the password, or alter prices and orders. It is not secure admin authentication.
- The dashboard's change-password action uses native browser prompts. The integrated headless browser used here does not support `prompt()`, so that action was not verified in this environment; test it in the buyer's target browser or replace it with an in-page password form.
- Browser data is not shared across devices and can be cleared or edited. Do not use local totals, rewards, promo eligibility, inventory, reviews, or order status as a source of truth for real money or fulfillment.
- The website HTML's checkout does not send its orders to `script2.py`; it marks demo orders accepted in local storage.

## The Python service is local demo code

- `script2.py` binds the HTTP server to `127.0.0.1` (default port `8765`). Do not expose it directly to the internet or a shared network.
- `GET /api/orders` has no authentication and returns saved Telegram order records, which include customer contact/location details. If the service were exposed beyond the local machine, those records could be disclosed.
- `POST /api/orders` checks request size and a few required top-level fields, but does not validate item prices, totals, discounts, inventory, or the full order schema. It has no admin authentication, session protection, or rate limiting.
- The Telegram bot token is read from the `TELEGRAM_BOT_TOKEN` environment variable; the code contains no token. The buyer must issue/rotate the token and keep it outside the files.
- The bot presents cash and “Online Payment (Click / Payme)” choices, but no provider invoice/API integration was found. The selected label is recorded with the order; it is not proof of payment.
- The bot writes Telegram orders to `telegram_orders.json` beside the script at runtime. That file can contain personal data and needs access controls, retention rules, and backups if it is ever used beyond the demo.
- No pinned dependency manifest was supplied. The buyer must choose and test a compatible `aiogram` package/version and Python runtime.

## Required before any real launch

Move trust and persistence to a maintained backend before accepting real orders:

1. Recalculate prices, fees, discounts, reward balances, and totals server-side from an authoritative menu; reject client-supplied totals.
2. Validate and normalize all order fields, menu IDs, quantities, availability, promo eligibility, and order transitions on the server.
3. Implement admin authentication with server-side sessions, authorization, secure password reset, and appropriate CSRF protections.
4. Add rate limiting, abuse controls, audit logs, secure transport, and monitoring. Restrict and protect access to customer order data.
5. Keep bot/payment/provider secrets in a managed environment or secret store and rotate any credentials that may have been used by the seller.
6. Integrate a real payment provider using its verified server-side flow, webhooks, idempotency, and reconciliation. Do not treat a selected payment method as a completed payment.
7. Decide how customer data is retained, backed up, exported, and deleted, and provide appropriate privacy notices.
8. Deploy behind a properly configured production web server and test the complete Telegram/backend/payment flow in that environment.

## What was tested

- `telegramm.html` was tested as a local browser demo in Uzbek, English, and Russian: 12 menu items per language, cart, promo application, checkout, theme switching, owner first-run setup and hash storage, owner login, and no browser console/page errors.
- Responsive layout was compared at desktop and mobile widths. This is a browser smoke test, not a full accessibility, security, performance, or device-compatibility audit.
- XSS-style values in locally stored review/order fields were confirmed to render as text rather than markup.
- The dashboard's native-prompt password-change interaction was not exercised because the integrated browser does not support `prompt()`.
- `script2.py` passed a Python syntax check. It was not started with a real token, connected to Telegram, or tested against a payment provider or production network.
- No real payment, customer transaction, production order fulfillment, or deployment was tested.

The original `endofproject.html` was used only as a comparison baseline and is not safe to transfer. Do not include it with the buyer's files.
