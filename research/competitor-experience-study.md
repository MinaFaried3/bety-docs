# Bety competitor experience study

**Research date:** 27 October 2026

**Purpose:** Inform a new Bety plan while preserving the [original plan](../bety-business-and-experience-plan.md).

**Deliverables:** [Competitor-informed Bety plan](../bety-competitor-informed-plan.md) · [Flow and edge-case catalog](../bety-flow-edge-case-catalog.md)

## 1. Evidence method and limits

This study combines all 14 user-provided Tablya screenshots, first-party app descriptions and help/terms pages, and a limited read-only inspection of Breadfast's public Chef on Demand website. No account was created, no order was placed, and no payment was made. Authenticated Talabat/Breadfast mobile flows and competitor back-office systems were not exercised.

Use four evidence labels:

- **Observed:** A control, text, or state directly visible in the uploaded screenshots or public browser inspection.
- **Documented:** A capability or policy described by the competitor's first-party public material.
- **Inferred:** A plausible interpretation that still needs a live test.
- **Bety proposal:** An original product or operating decision; it is not a claim about a competitor.

Public help articles can be older than the current app. Regional availability and experiments can change an experience. A screenshot proves a visible state, not a successful transaction or the behavior behind a button. App-store reviews are individual reports, not verified incidents or representative failure rates.

The reference screenshots contain private account/address information. Exact reference copies and [file hashes](../references/tablya/screenshot-manifest.json) are already tracked in the repository's existing reference commit. This study does not reproduce the account name, phone number, or precise address. Use redacted derivatives for external presentations; this documentation change does not alter the existing reference files or their history.

## 2. Talabat: verified patterns and useful lessons

### TA01 — Discovery, saved context, and repeat purchase

Talabat's Egypt App Store description documents search/filtering, merchant menus, cash/card payment, saved addresses, scheduling, tracking, notifications, offers, and reorder. This supports a familiar customer mental model: choose destination, browse supply, configure items, review basket, pay, track, and repeat. The description does not verify the current position or appearance of every control. [Talabat Egypt App Store listing](https://apps.apple.com/eg/app/talabat-food-grocery-more/id451001072).

**Bety proposal:** Use that sequence, but make cook identity, portions, preparation state, and the actual meal date more explicit. A customer's remembered address and past order are shortcuts that still require current availability checks.

### TA02 — Serviceability, merchant acceptance, and financial clarity

Talabat's Egypt terms describe address-dependent merchant availability, a merchant-acceptance boundary for cancellation, support for post-acceptance cancellation requests, fee breakdown before checkout, and handling of failed delivery or missing/defective items. The terms also describe pickup where offered. [Talabat Egypt terms](https://www.talabat.com/egypt/terms).

**Bety proposal:** Make serviceability and an authoritative commitment boundary explicit. Show a final payable total before collecting money. Resolve customer problems through Bety and allocate responsibility internally. Pickup is a separate eligibility-controlled mode, particularly because cooks may operate at private household locations.

### TA03 — End-to-end support and seller tools

Talabat's corporate FAQ describes the browse/cart/checkout sequence, tracking, in-app customer support, and partner tools for menus, orders, and performance. It is a broad capability reference rather than a specification for Egypt's exact screen hierarchy. [Talabat corporate FAQ](https://corporate.talabat.com/faq/).

**Bety proposal:** Build both sides of the marketplace. A polished customer home without a usable cook production board, support queue, and financial record is incomplete.

### TA04 — Conflicting public guidance

The public Egypt FAQ gives fixed cancellation timing and says delivery is the only possible extra charge. The Egypt terms instead describe acceptance-dependent cancellation and several possible fees. This is a documented inconsistency between pages, not evidence about which rule the current app applies. [Egypt FAQ](https://www.talabat.com/egypt/faq), [Egypt terms](https://www.talabat.com/egypt/terms).

**Bety proposal:** Derive checkout, help content, cancellation preview, support tools, and seller explanations from one versioned policy. Do not copy a competitor's old time limits or refund wording into Bety's terms.

## 3. Breadfast: verified patterns and useful lessons

### BF01 — Everyday utility and planned shopping

Breadfast's Egypt App Store listing presents immediate or scheduled grocery fulfillment and several adjacent services. That establishes a convenience and repeat-shopping benchmark; it does not establish that a distributed home-cook marketplace can meet the same speed or logistics model. [Breadfast Egypt App Store listing](https://apps.apple.com/eg/app/breadfast-groceries-and-more/id1288436997).

**Bety proposal:** Reduce repeated decisions through saved preferences, familiar categories, persistent quantity controls, and reordering. Keep the product focused on home-style meals rather than copying unrelated verticals.

### BF02 — Scheduling as an explicit checkout choice

A Breadfast delivery help article describes choosing a schedule and available time slot during checkout. Its modification date is August 2022, so the precise current mobile navigation needs revalidation. [Breadfast delivery scheduling help](https://freshdesk.breadfast.com/en/support/solutions/articles/69000775524-how-long-does-it-take-for-my-order-to-arrive-).

**Bety proposal:** Display the selected date/window earlier, while allowing an eligible change at checkout. Customers must know whether they are ordering tonight for tomorrow.

### BF03 — Capacity must affect the promise

Breadfast's August 2022 busy-state article links temporary unavailability to delivery workload and its then-stated service target. Treat those specific timings as historical public guidance. [Breadfast busy-state help](https://freshdesk.breadfast.com/en/support/solutions/articles/69000775523-why-am-i-seeing-a-sorry-we-re-busy-message-when-i-place-my-order-).

**Bety proposal:** Offer an actual next available slot instead of a vague retry message. Do not accept an order when production or delivery capacity cannot support the promise.

### BF04/BF05 — Changes, cancellation, and preparation state

Breadfast's modification article, dated August 2022, directs users toward cancellation/reorder rather than editing. Its cancellation article, updated October 2024, describes cancellation before the prepared state through order history, with support available afterward. [Modification help](https://freshdesk.breadfast.com/en/support/solutions/articles/69000775520-can-i-modify-an-order-after-it-was-placed-), [Cancellation help](https://freshdesk.breadfast.com/en/support/solutions/articles/69000775521-can-i-cancel-a-placed-order-).

**Bety proposal:** Avoid silent edits to paid orders. Calculate any allowed change against production, stock, slot, price, and payment state. Show the refund result before a customer confirms cancellation.

### BF06 — Rewards are a later retention mechanism

Breadfast's public help index documents points, rewards, levels, and redemption. Many entries are dated 2023, so current rates and benefits are not asserted here. [Breadfast rewards help index](https://freshdesk.breadfast.com/en/support/solutions/folders/69000636495/page/2?url_locale=en).

**Bety proposal:** Earn repeat use through consistent meals and reliable service before introducing a points liability. A reminder, saved cook, or reorder shortcut may solve the customer's need with less complexity.

### BF07 — Delivery data and account choices

Breadfast's privacy policy describes account/service information, delivery-related location processing, support, and account privacy choices. This is a reference for identifying necessary flows; it is not a privacy template or authority for Bety to collect the same data. [Breadfast privacy policy](https://www.breadfast.com/privacy-policy/).

**Bety proposal:** Minimize household and identity exposure. Separate operational messaging, optional marketing, and precise-location permissions. Keep private kitchen locations away from general discovery.

### BF08 — Chef on Demand is an adjacent, different business

Read-only inspection of the public website showed chef discovery, profiles, availability-related presentation, login, and categorized help. An expanded service FAQ states that cooking takes place at the customer's location, with tools/ingredients supplied by the customer and cleanup included. This is a chef visit, not the same fulfillment model as delivered meals cooked at the seller's approved premises. [Breadfast Chef on Demand FAQ](https://chefs.breadfast.com/greater_cairo/faq).

**Bety proposal:** Borrow the clarity of identity, specialty, availability, and booking expectations. Do not add home visits to Bety's meal checkout. They would require separate safeguarding, pricing, staffing, privacy, and cancellation design.

## 4. Tablya: all 14 screenshots examined

The filenames below are stable evidence identifiers. Capture timestamps in the status bar do not establish the app version or capture date. Personal details are intentionally omitted from the descriptions.

### T01 — IMG_3577.PNG: home and shopping intent

**Reference:** [Open screenshot](../references/tablya/screenshots/IMG_3577.PNG).

**Observed:** An address/fulfillment header; search for a kitchen or meal; chat and cart entry; promotional carousel; six intent/category tiles; nearby kitchens; and a three-item home/orders/account navigation bar. The visible intents include a one-hour category, cooked meals, food to finish cooking, offers, healthy, and catering.

**Not established:** Whether all intents are available at that address, whether the one-hour claim holds for each item, or whether the cart spans kitchens.

**Bety proposal:** Keep intent-based discovery, but separate preparation state, arrival promise, meal category, and merchandising tags. One item can have multiple tags without those concepts becoming interchangeable.

### T02 — IMG_3578.PNG: address source selection

**Reference:** [Open screenshot](../references/tablya/screenshots/IMG_3578.PNG).

**Observed:** A bottom sheet offers a detailed address entry, another map-selected location, and a currently selected location. The background remains visible and a close action exists.

**Not established:** Permission denial behavior, pin validation, saved-address persistence, or whether a destination change invalidates the basket.

**Bety proposal:** Use manual location as an equal first-class route. GPS is a suggestion, while the customer's confirmed delivery address determines catalog, fees, and delivery slots.

### T03 — IMG_3579.PNG: kitchen hero and closed state

**Reference:** [Open screenshot](../references/tablya/screenshots/IMG_3579.PNG).

**Observed:** Kitchen hero/logo, favorite/cart controls, a closed badge, rating/count, distance, food categories, preparation time, dish count, location summary, menu-category chips, discounts, item add controls, and a sticky existing-cart bar.

**Not established:** Whether add controls actually accept a purchase while closed, whether scheduled orders remain available, or whether the existing basket belongs to this kitchen.

**Bety proposal:** Distinguish closed now, busy, sold out, unavailable at this address, and open for future orders. Any active-looking action must lead to a valid available slot or explain the block.

### T04 — IMG_3580.PNG: menu browsing while scrolling

**Reference:** [Open screenshot](../references/tablya/screenshots/IMG_3580.PNG).

**Observed:** Compact kitchen heading, category chips, menu sections, product photos, descriptions, prices/discounts, add controls, and a persistent cart action.

**Not established:** Whether chips jump to a section, filter the list, or remain synchronized with scrolling.

**Bety proposal:** Define that behavior explicitly: chips navigate to sections, active state follows the visible section, and the list restores its position when a meal sheet closes.

### T05 — IMG_3581.PNG: meal customization sheet

**Reference:** [Open screenshot](../references/tablya/screenshots/IMG_3581.PNG).

**Observed:** A modal product view has a hero, favorite/cart/close actions, dish description, preparation time, a required single-choice weight group, variant prices/discounts, quantity control, and an add action displaying a price.

**Not established:** Stock by variant, behavior with no selected option, price recalculation, allergen handling, or what tapping the cart does to an unsaved selection.

**Bety proposal:** Require explicit valid choices, identify weight per unit, show line total for quantity, and make discount differences across sizes clear. Do not call unusual visible variant pricing a bug without testing it.

### T06 — IMG_3582.PNG: time-intent results

**Reference:** [Open screenshot](../references/tablya/screenshots/IMG_3582.PNG).

**Observed:** A one-hour results heading and kitchen count, scoped search, nearest sort, category tiles, kitchen groups containing horizontal product cards, and a persistent basket bar.

**Not established:** Whether the count reflects currently deliverable kitchens, how ETA is computed, or whether every product inherits the heading's promise.

**Bety proposal:** Admit an item into an express collection only when its full preparation-plus-delivery promise fits the selected address, current capacity, and safe handling limits.

### T07 — IMG_3583.PNG: category results across cooks

**Reference:** [Open screenshot](../references/tablya/screenshots/IMG_3583.PNG).

**Observed:** A poultry category page uses scoped search/sort and kitchen-grouped product carousels with prices and quick-add controls.

**Not established:** Required modifiers, availability revalidation, or cross-kitchen cart conflict behavior.

**Bety proposal:** Keep seller identity on cross-kitchen product cards. Quick add opens configuration whenever a meal has required choices; it never invents a default.

### T08 — IMG_3584.PNG: another kitchen's profile

**Reference:** [Open screenshot](../references/tablya/screenshots/IMG_3584.PNG).

**Observed:** A larger menu, preparation-time summary, ratings, distance, kitchen identity, location summary, category chips, offers, and a sticky cart.

**Not established:** Whether the summary time is a kitchen default, a dish maximum, or a full delivery promise.

**Bety proposal:** Label preparation time separately from arrival time. Show a coarse service neighborhood for household privacy and only the seller disclosures required for the approved business model.

### T09 — IMG_3585.PNG: portions and ambiguous choice descriptions

**Reference:** [Open screenshot](../references/tablya/screenshots/IMG_3585.PNG).

**Observed:** Menu descriptions include approximate people served and alternative components such as a protein or sauce choice. Images, add controls, prices, and category chips remain visible.

**Not established:** Whether alternatives in the text become structured choices later or how a cook receives them.

**Bety proposal:** A selectable protein/sauce becomes a validated modifier with explicit price, stock, and allergen effects. Approximate serving guidance accompanies a measured portion definition.

### T10 — IMG_3586.PNG: account and help

**Reference:** [Open screenshot](../references/tablya/screenshots/IMG_3586.PNG).

**Observed:** A prominent WhatsApp help entry, editable identity/contact items, address book, favorites, password settings, OS-notification guidance, FAQ, app-rating action, and legal links.

**Not established:** Account deletion, phone-change verification, in-app case history, or delivery-notification reliability.

**Bety proposal:** Retain accessible help but preserve order-linked cases inside Bety. Phone changes need verification; notification denial must not hide order state. Provide privacy/deletion controls and a support fallback.

### T11 — IMG_3587.PNG: scrolled kitchen discovery

**Reference:** [Open screenshot](../references/tablya/screenshots/IMG_3587.PNG).

**Observed:** Multiple kitchen groups with photos, categories, products, original/sale prices, and a new-kitchen label. Bottom navigation overlays part of the scrolled content.

**Not established:** Ranking rules, sponsored placement, the definition of “new,” or whether the overlap is intentional styling.

**Bety proposal:** Explain new-kitchen status and label paid promotion. Reserve layout space for bottom navigation/cart controls so essential content and actions remain reachable.

### T12 — IMG_3588.PNG: nearby supply and unrated sellers

**Reference:** [Open screenshot](../references/tablya/screenshots/IMG_3588.PNG).

**Observed:** Nearby-kitchen sections include product rows and new/unrated presentation. The address and search remain prominent.

**Not established:** Whether distances follow straight-line or road distance, or how seller eligibility affects visibility.

**Bety proposal:** Use distance only as a proximity signal and arrival estimates from actual fulfillment assumptions. Give new assessed sellers a clear “new” state rather than inventing a rating.

### T13 — IMG_3589.PNG: cart, fulfillment, recurring choices

**Reference:** [Open screenshot](../references/tablya/screenshots/IMG_3589.PNG).

**Observed:** One cart line, quantity controls, clear-cart action, add-more action, delivery versus kitchen pickup, one-time/weekly/monthly choices, displayed savings, and a submit action.

**Not established:** Whether recurring plans auto-renew, whether seven/thirty means every calendar day, whether future supply is reserved, how delivery is priced per occurrence, or whether pickup is safe/eligible for every kitchen.

**Bety proposal:** Separate a one-time meal, a finite meal bundle, and a service membership. Each has a different commitment and refund model. Do not activate recurring options before those details work.

### T14 — IMG_3590.PNG: incomplete address and fee state

**Reference:** [Open screenshot](../references/tablya/screenshots/IMG_3590.PNG).

**Observed:** The cart asks the customer to choose a delivery address, allows a short note, and shows a delivery charge described as determined by the kitchen. The visible total matches the food amount in that state, and the submit action remains visible.

**Not established:** Whether submission is blocked, whether another screen confirms fees, or whether payment happens later. This is not enough evidence to call the checkout broken or to conclude a charge is hidden.

**Bety proposal:** Distinguish a basket subtotal from a binding payable quote. Do not present an incomplete fee calculation as a final total. Collect address/slot and show the exact accepted total before a payment commitment.

## 5. Unseen flows that must still be designed

The screenshot set does not establish onboarding/authentication steps, password reset behavior, map editing, checkout payment selection, payment callbacks, kitchen acceptance, delivery tracking, recurring-plan management, cancellation outcomes, refund completion, seller onboarding, production controls, courier tools, settlement, or administration.

These are defined as Bety requirements in the new plan and edge catalog, without inventing Tablya implementations. Customer-visible controls in screenshots are reference material, not instructions to reproduce their copy, imagery, brand, or business promises.

The Tablya listing describes a home-cook marketplace and includes individual reviews mentioning location selection, payment/chat responsiveness, and notifications. Developer responses say reported issues were addressed. These are useful prompts for Bety regression scenarios, not verified current defects or comparative reliability statistics. [Tablya Egypt App Store listing](https://apps.apple.com/eg/app/tablya-homemade-food/id6794864990).

## 6. Flow adoption map

- **Destination:** Talabat's address-dependent availability + T02's accessible location sheet → confirmed delivery context and a basket impact preview.
- **Discovery:** Talabat's search/menu model + Breadfast's repeat-shopping emphasis + T01/T06/T07/T11/T12 → kitchen and meal discovery under one address/date context.
- **Menu:** T03/T04/T08/T09 → sticky section navigation, meaningful portions, seller identity, valid closed states.
- **Configuration:** T05 → explicit variants/modifiers and correctly priced quantities.
- **Cart:** T13/T14 + Talabat's pre-checkout fee breakdown → one clear binding quote, with a defined one-kitchen conflict policy.
- **Scheduling:** Breadfast's documented slot choice → early date/window selection and capacity reservation.
- **Payment:** Public competitor capabilities → Bety's own verified, idempotent payment and recovery design.
- **Order management:** Talabat's tracking/reorder and Breadfast's state-related cancellation → truthful state, eligible actions, and deliberate repricing for changes.
- **Help:** T10 and documented in-app support → one case history with an urgent safety path and human escalation.
- **Cook operations:** Talabat's public seller-tool capabilities + Bety's food business requirements → a separate application, production, earnings, and compliance experience.
- **Retention:** Breadfast's repeated-use/rewards reference + T13's recurring intent → favorites/reorder first, finite bundles later, membership only if economics justify it.

## 7. Research backlog before final UI sign-off

Run a consented, hands-on Egypt mobile comparison on representative current versions and addresses. Inspect permission denial, guest browse, authentication return path, filters, modifiers, cart conflict, address change, all-in fees, scheduling, payment pending, confirmation, tracking, help, cancellation, refund status, reorder, and account deletion.

Record app version, platform, date, region, preconditions, action, observed result, and whether the behavior varies by merchant. Capture only necessary redacted evidence. Never create a paid order or recurring charge merely to complete research without a separate authorized test budget.

Unverified exact competitor interactions remain in this backlog. Bety's proposed flows can still be designed and tested now; their acceptance criteria do not depend on assuming a competitor behaves a certain way.
