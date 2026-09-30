# ManteeTech — Production Storefront Master Prompt

Copy everything inside the prompt below into your coding agent. Attach the supplied marketplace ZIP and Mantee logo when you submit it.

---

## MASTER PROMPT

Act as a senior product designer, commerce architect, application-security engineer, and frontend/backend engineer. Rebuild the supplied ManteeTech marketplace starter into a polished, responsive, production-minded **single-vendor online store** for phones, gadgets, and technology accessories. This is one retailer's catalogue and one retailer's stock—not a seller marketplace.

### How to work

1. Inspect the supplied ZIP, logo, and existing files before changing anything. Reuse sound work and migrate useful catalogue, copy, and schema details; do not blindly replace working pieces or extract the ZIP over unrelated files.
2. Build the working application, not just a plan, visual mockup, or collection of disconnected screens. Connect every visible control to a real interaction and persistent data source. Do not leave checkout, search, admin, or product actions as deceptive demo buttons.
3. Keep the experience an app-like SPA, with direct-loadable, shareable product and category URLs. Use a modern, typed React stack with reusable components, tested routing, and a maintainable data layer. Prefer React + TypeScript + Vite + React Router for the client. Make public pages crawlable with server rendering or build-time prerendering for the home page, category pages, and product pages; a hash-only or client-rendered-only storefront is not an SEO-complete solution.
4. Preserve a clear demo/development mode, but visibly label sample data and disable live payment until real configuration is supplied. Never pass sample prices, stock, imagery, reviews, or claims off as ManteeTech's verified live catalogue.
5. Make sensible technical decisions without pausing for approval on routine implementation details. Where real store policy, business details, credentials, or inventory are unknown, create clearly named configuration fields and safe defaults; document exactly what the owner must supply. Never invent a delivery promise, warranty, return policy, business address, product specification, rating, certification, or “in stock” claim.
6. Finish with a working build, meaningful tests, and a concise setup guide. Report what is implemented, what was actually tested, and every remaining owner-supplied item. Do not call it production-ready while payment, secrets, store data, security rules, or deployment configuration remain unverified.

### Brand system and art direction

Use the attached **Mantee Enterprises / ManteeTech** logo as the authoritative identity. Preserve the logo artwork; do not redraw or distort it. Place the supplied image in the project as an optimized brand asset and use it in the header, footer, favicon/app icon where appropriate, and social sharing image when licensing/format permits. Use the readable wordmark “ManteeTech” in interface text and the descriptor “Phones, Gadgets & Tech” where it fits.

Create one source of truth named `BRAND_THEME` (or equivalent) for brand name, tagline, logo asset, currency, and semantic colors. Distribute it through CSS custom properties/design tokens used by every storefront, account, checkout, and admin component. Do not scatter hex values through component styles. The logo suggests:

- **Deep navy / near-black teal** for primary text, dark surfaces, and primary actions (approximately `#0C2533`).
- **Deep teal** for supporting emphasis (approximately `#174741`).
- **Fresh green** for primary brand accents and success states (approximately `#51B764`).
- **Mint/teal** as a restrained secondary accent (approximately `#4BB19B`).
- **White and very pale mint/neutral** for spacious surfaces and legible product imagery.

These are starting points sampled from a glowing JPEG logo, not immutable exact brand standards. Check contrast and adjust shades for WCAG AA; never use bright green for long body copy on white. Keep glow effects in the logo/hero art direction, not behind ordinary text or every card. Add a real, keyboard-accessible light/dark theme preference only if it remains readable and coherent. A single brand configuration change must propagate consistently across the UI.

Visual direction: premium, confident, modern Nigerian technology retailer. Use strong editorial type hierarchy, generous but efficient spacing, crisp product photography, carefully aligned cards, restrained radii/shadows, clear price emphasis, and quick, purposeful motion. Avoid generic template aesthetics, crowded gradients, decorative emoji, low-contrast text, fake trust badges, made-up ratings, and mobile hover-only controls.

### Product experience and screens

Build the complete customer journey with responsive layouts—not just a homepage:

- **Global shell:** dismissible, configurable announcement strip; sticky header with logo, Shop/category navigation, prominent search, account, saved-items and accessible bag/cart count; mobile menu and tap targets; footer with editable contact, policies, support, social links, and newsletter consent.
- **Home:** clear value proposition and primary “Shop” action; strong campaign/featured-product hero using real product imagery; browsable category tiles; featured, new, and popular catalogue sections based only on valid data; useful delivery/payment/service information sourced from editable store settings; newsletter sign-up with consent and success/error states.
- **Shop and category:** responsive product grid, result count, breadcrumb, search field, category/brand filters, filters for price range, availability, condition and genuine product attributes where data exists, sorting (featured, newest, price, name), active-filter chips, reset-all, empty/error/loading states, and accessible pagination or “load more.” On mobile, use a usable filter drawer/bottom sheet and keep sort/search easy to reach. Reflect search, filters, and sort in URL query parameters so views can be bookmarked and shared.
- **Advanced search:** debounced search with useful suggestions and keyboard navigation; search product name, brand, model, SKU, category, and relevant specs; tolerate common spelling variations where feasible; allow filtering by category, brand, price, stock, and genuine attributes; preserve search on navigation and show helpful empty results. Do not use “AI search” as a label unless an actual, configured service powers it; standard search must work without an AI key.
- **Product detail:** stable `/products/:slug` URL; image gallery with alt text; product name, brand/model, current and comparison price only when valid, stock state, selectable variants only when actually available, quantity control, add-to-cart and buy-now, concise selling points, full verified specs, delivery/returns content from store settings, related products, and shareable canonical metadata. Never fabricate reviews or stock urgency.
- **Cart and checkout:** persistent cart with quantity and stock validation, remove/save-for-later, subtotal, transparent configurable shipping/fees, promo codes only if implemented, and order total. Provide guest checkout and optional customer account without forcing sign-up. Validate contact and delivery fields, show a clear review step, recover gracefully from abandoned/failed payment, prevent duplicate orders, and provide confirmation plus a privacy-safe order lookup or signed tracking mechanism.
- **Accounts:** secure sign-up/sign-in, email verification, password reset, sign-out, profile/address management, saved products synced to account, order list/detail, and clear session-expiration behavior. Guest order data must not be exposed by guessable IDs.
- **Store admin:** separate protected operations UI for dashboard, search/sort/filter catalog, create/edit/archive products, category/brand/spec management, image management, variants, stock adjustments, low-stock view, order review/status transitions, customer support details as authorized, discounts/promotions if included, store settings, and an audit trail for sensitive actions. Validate inputs and show save/error/loading states. Include CSV import/export with schema validation and a preview/rollback path; never publish an import silently.
- **Trust and support pages:** contact/support, delivery, returns/refunds, privacy, terms, and about pages. Put business-specific copy in editable settings and label anything still awaiting owner approval. Add a real 404 page and route-level error boundaries.

### Catalogue and data rules

Design the schema for at least 50 products and seed **about 50 useful catalogue records** across smartphones/tablets, power and charging, audio, wearables, protection, storage, and other owner-approved technology categories. Use the supplied starter's 19 records as migration/reference material, not proof of current availability. Do not fabricate real inventory, seller relationships, stock, or authoritative specs. If the owner has not provided the remaining verified catalogue, mark generated entries conspicuously as sample/draft data, keep them out of live checkout and production search indexing, and provide a simple import path for the real catalogue.

Use normalized, typed product/category/brand data with stable IDs and unique SEO slugs. Products should support description, brand, SKU, category, images with alt text, price, optional valid compare-at price, active/draft/archived status, stock, variants, structured specifications, created/updated timestamps, and SEO title/description. Store currency as **NGN**, show Naira consistently, and centralize integer-Naira to Paystack minor-unit conversion on the server. Do not trust price, discount, stock, shipping cost, role, or order total sent by the browser.

### Payments, fulfilment, and Nigeria-specific behavior

Use Supabase Auth + Postgres/RLS and server-side Supabase Edge Functions (or an equally secure server API) if the existing Supabase setup is retained. Paystack is the intended online-payment provider because the starter already references it. Keep provider integration behind a well-defined server-side payment boundary.

- Initialize transactions on the server using the canonical order amount, customer email, NGN currency, and a unique idempotency-safe reference.
- Create/validate the pending order atomically against current active products, authoritative prices, available quantities, and server-configured shipping/discount rules.
- Mark an order paid **only after server-side verification** that the provider reference, amount, currency, status, and intended order all match. Verify webhook signatures; make callbacks/webhooks idempotent; prevent reference replay, mismatched-order updates, duplicate fulfilment, and arbitrary status transitions. Do not trust a browser success callback.
- Reserve/decrement stock atomically at a deliberate, documented point in the verified order flow, and release reservations safely on cancellation/expiry. Protect against overselling under concurrent purchases.
- Configure Lagos/nationwide delivery zones, fees, ETAs, pickup, cash-on-delivery, and returns only when the business owner confirms those choices. Otherwise display clear “configure before launch” messaging in admin, not invented promises at checkout.
- Provide payment pending/success/failure/close/retry states; never clear the cart or claim payment success before confirmation. Store minimal payment metadata, never raw card details.
- Keep Paystack secret keys, Supabase service-role keys, webhook secrets, and email-provider credentials exclusively in Replit Secrets/server environment. Only genuinely public keys may be delivered to the browser.

### Security and privacy — required, not optional

Treat customer and payment data as sensitive. Threat-model authentication, authorization, admin access, checkout, uploads, and public endpoints. Implement and document:

- Least-privilege database roles and tested RLS for every table and storage bucket; public users can read only active public catalogue fields, customers can access only their own profile/orders/items/saved data, and admins get narrowly scoped server-enforced permissions.
- **No user-editable admin role:** customers must never be able to promote themselves by updating their profile or calling a public RPC. Grant/revoke staff access through a trusted server-side owner-controlled process; protect staff accounts with MFA where supported.
- Server-side schema validation and authorization for every mutation; atomic database transactions for inventory, checkout, and order status; rate limits/abuse protection on auth, checkout, search endpoints as appropriate, newsletter, and uploads; safe file type/size validation and private-by-default storage.
- Secure cookies/session handling appropriate to the chosen auth setup, CSRF protection where applicable, strict origin/CORS allowlists, secure headers (CSP, HSTS in production, frame/content-type/referrer protections), safe redirect validation, and no secrets or personal data in URLs, logs, analytics, client errors, or source maps.
- Output escaping and safe URL handling; no unsafe HTML rendering of user/catalogue content; dependency audit and minimal permissions; request timeouts and bounded payloads.
- Configurable privacy consent for analytics/marketing, unsubscribe support, data minimization, retention/deletion workflows, and owner-reviewed privacy/terms copy. Do not claim legal compliance certification.
- Production-safe error responses that do not leak stack traces, SQL/provider details, credentials, or whether another user account exists.

### SEO and AI-search readiness

Build search engine fundamentals into the routes and content: unique human-readable product/category URLs; server-rendered or pre-rendered indexable HTML for public catalogue routes; unique titles/descriptions; canonical URLs; Open Graph/Twitter metadata; sitemap.xml generated from active public products/categories; accurate robots.txt; breadcrumbs; semantic headings and links; compressed responsive images with width/height, modern formats where possible, and lazy-loading below the fold.

Add valid JSON-LD where facts exist (`Organization`/`WebSite`, `BreadcrumbList`, `Product`, and `Offer` with correct currency, price and availability). Ensure structured data exactly matches visible, verified page content. Include product/category copy and structured attributes that help both search engines and answer engines understand what the store sells. No keyword stuffing, hidden text, fake aggregate ratings, fabricated local-business address, false stock/price, doorway pages, or promise of rankings. Keep sample products `noindex` and excluded from sitemap until verified for publication.

### Accessibility, speed, and responsive quality

Meet WCAG 2.2 AA intent: semantic landmarks, logical headings, keyboard-complete navigation, visible focus, screen-reader labels/live feedback, accessible dialogs/drawers with focus management and Escape handling, properly associated form labels/errors, sufficient contrast, reduced-motion support, and no color-only meaning. Test with keyboard and an automated accessibility checker.

Design from narrow mobile upward. Support small phone, large phone/tablet, laptop, and wide desktop without horizontal page overflow. Use responsive image sizes, lazy loading, route/code splitting where useful, skeletons that respect reduced motion, optimistic updates only with rollback, and helpful offline/network-error feedback. Keep a minimum comfortable touch target around 44×44 CSS px.

### Quality gates and delivery

Add a short README with architecture, local run steps, migrations/seed instructions, Replit Secrets names, deployment/SPA fallback or prerender configuration, payment/webhook setup, catalog import format, admin provisioning, demo-vs-live safeguards, backup guidance, and launch checklist. Include `.env.example` with names only—no real values.

Add meaningful automated checks: typecheck, lint, production build, unit tests for filtering/pricing/formatting/validation, server tests for authorization/order/payment verification/idempotency/inventory concurrency, and browser tests for mobile/desktop browsing, search/filter/reset, add/remove/update cart, guest checkout failure/success simulation, account flows, admin denial for customers, authorized product changes, and direct-loading SEO routes. Use test keys/mocks only. Never test against live payment or send real customer communications without explicit authorization.

Before declaring completion, run the available checks, fix failures, and state which checks actually ran. Inspect at least 360 px mobile and desktop layouts; run a Lighthouse/accessibility pass if tooling is available and report the actual results. Keep test data separate from production. Provide a final launch checklist for the owner to supply and verify: legal business details/contact channels, approved logo usage, real product catalogue/images/prices/stock/specs, delivery zones/fees/ETAs, returns/warranty policy, Supabase project and RLS, admin identity/MFA, Paystack live credentials/webhook URL/signature, domain/HTTPS, transactional email sender, privacy/terms wording, and monitoring/backups.

**Success means:** an attractive, fast, keyboard-usable store that customers can browse and buy from on mobile or desktop, with a genuinely operable protected admin, a verified server-side payment path, trustworthy catalogue data, indexable public products, and no misleading demo behavior—not merely a good-looking front page.

---

## Build-agent handoff note

The supplied starter is a vanilla HTML/CSS/JS prototype with 19 demo products. Its existing README lists unfinished password reset, product edit/archive, payment verification/webhooks, delivery/receipt emails, fulfillment/audit, rate limiting, and automated end-to-end testing. Its current profile policy allows users to update their own profile row, so admin role changes must be separately blocked at the database/server level—not only hidden in the UI. Treat the included client payment callback and the broad-CORS payment verification function as untrusted starter code; replace them with a complete server-verified flow. The current ZIP is a starting point, not evidence that any real checkout or security control is production-safe.