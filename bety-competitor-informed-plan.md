# Bety — بيتى
## Competitor-informed business, experience, and operations blueprint

**Version:** 2.0 proposal

**Prepared:** 27 October 2026

**Market:** Egypt · Arabic-first (`ar-EG`) with English (`en-US`)

**Currency/timezone:** EGP · Africa/Cairo

**Document status:** A separate proposed plan. The [original business plan](./bety-business-and-experience-plan.md) is preserved unchanged. This blueprint develops a more familiar shopping experience and explicitly designs the additional modes suggested by competitor research; it does not silently activate them or replace signed commercial policies.

**Read with:** [Competitor research and all 14 screenshot reviews](./research/competitor-experience-study.md) · [Flow and edge-case catalog](./bety-flow-edge-case-catalog.md).

> **Direction:** Make finding, configuring, buying, and repeating a meal feel familiar to a Talabat or Breadfast customer, while making the home cook, portion, preparation state, meal date, and accountability clearer for Bety's particular business.

## Contents

1. [Business direction and competitive edge](#1-business-direction-and-competitive-edge)
2. [Research conclusions and product decisions](#2-research-conclusions-and-product-decisions)
3. [Experience model and release boundaries](#3-experience-model-and-release-boundaries)
4. [F01 — Arrival, identity, and returning to intent](#4-f01--arrival-identity-and-returning-to-intent)
5. [F02 — Address, serviceability, and location changes](#5-f02--address-serviceability-and-location-changes)
6. [F03 — Meal date, delivery window, and shopping intent](#6-f03--meal-date-delivery-window-and-shopping-intent)
7. [F04 — Home, navigation, and merchandising](#7-f04--home-navigation-and-merchandising)
8. [F05 — Search and relevant discovery](#8-f05--search-and-relevant-discovery)
9. [F06 — Categories, filters, sorting, and collections](#9-f06--categories-filters-sorting-and-collections)
10. [F07 — Kitchen and cook profile](#10-f07--kitchen-and-cook-profile)
11. [F08 — Meal details, variants, and add to cart](#11-f08--meal-details-variants-and-add-to-cart)
12. [F09 — Cart, saved baskets, and kitchen conflicts](#12-f09--cart-saved-baskets-and-kitchen-conflicts)
13. [F10 — Prices, offers, and complete totals](#13-f10--prices-offers-and-complete-totals)
14. [F11 — Checkout and schedule commitment](#14-f11--checkout-and-schedule-commitment)
15. [F12 — Payment, confirmation, and uncertainty](#15-f12--payment-confirmation-and-uncertainty)
16. [F13 — Active orders and truthful tracking](#16-f13--active-orders-and-truthful-tracking)
17. [F14 — Changes and cancellation](#17-f14--changes-and-cancellation)
18. [F15 — Support, refunds, and safety reports](#18-f15--support-refunds-and-safety-reports)
19. [F16 — Reviews, favorites, and reorder](#19-f16--reviews-favorites-and-reorder)
20. [F17/F18 — Account, privacy, notifications, and messaging](#20-f17f18--account-privacy-notifications-and-messaging)
21. [F19 — Finite meal plans and recurring commitments](#21-f19--finite-meal-plans-and-recurring-commitments)
22. [F20/F21 — Pickup, requests, catering, and finish-at-home](#22-f20f21--pickup-requests-catering-and-finish-at-home)
23. [F22/F23 — Cook onboarding, menus, and availability](#23-f22f23--cook-onboarding-menus-and-availability)
24. [F24/F25 — Production, packing, couriers, and handoff](#24-f24f25--production-packing-couriers-and-handoff)
25. [F26/F27 — Settlement, administration, and safety control](#25-f26f27--settlement-administration-and-safety-control)
26. [F28 — Accessibility, interruption, and recovery](#26-f28--accessibility-interruption-and-recovery)
27. [Commercial model and sustainable economics](#27-commercial-model-and-sustainable-economics)
28. [Technology and implementation contracts](#28-technology-and-implementation-contracts)
29. [Deployment, rollout, and measurement](#29-deployment-rollout-and-measurement)
30. [Decision log and completion criteria](#30-decision-log-and-completion-criteria)

## 1. Business direction and competitive edge

### 1.1 The business

Bety is a managed Egyptian marketplace for home-style meals produced by mothers and independent cooks through legally approved production arrangements. The initial buyer is a household seeking a dependable lunch or dinner with familiar food, clear portions, and a known delivery date. The seller needs a useful route to demand, manageable commitments, safe operations, and understandable earnings.

The first zone should be compact and operationally accessible to the founder. Start with a small assessed supply group and a reviewed menu. Use scheduled preorders as the primary release. Express fulfillment is a conditional later capability supported by real available batches and delivery capacity.

Bety owns the customer's resolution path and marketplace operating standards. The actual food seller, production responsibilities, delivery role, collection arrangement, and merchant-of-record treatment must match approved contracts. A marketplace label does not establish regulatory exemption.

### 1.2 What should feel familiar

A customer can open the app, confirm an address, discover kitchens or dishes, make valid choices, adjust a persistent basket, see the full total, pay, track, get help, and reorder. The customer should not have to learn an unfamiliar procurement system just to buy dinner.

The interface can be efficient while the operations remain deliberate. A fast add button does not mean a meal arrives instantly; a remembered cart does not reserve stock indefinitely; and a saved cook is not automatically available every day.

### 1.3 Bety's proposed competitive edge

These are advantages to build and validate, not claims that competitors lack them:

1. **Portion confidence:** Measured quantities, included components, actual packed-meal photos, and approximate adult servings. Measure “less food than expected” complaints and repeat purchase.
2. **A visible meal date:** Date/window, cutoff, and preparation state stay visible from discovery to receipt. Measure wrong-day orders, abandoned checkout, and missed windows.
3. **Cook control and viable earnings:** Capacity caps, pause controls, batch planning, labor-aware costing, and transparent payout statements. Measure cook contribution after labor and payout accuracy.
4. **Trust with household privacy:** Explain assessment scope/date, ingredients, batch accountability, and support while keeping private household details restricted. Measure trust comprehension and privacy incidents.
5. **Fast recovery from uncertainty:** Payment-checking, order retrieval, case history, refund tracking, and one accountable support team. Measure duplicate payment attempts and unresolved case age.
6. **A useful household routine:** Favorite cooks, planned weekly menus, and quick repeat ordering before a complex subscription. Measure full-price repeat orders and cook capacity utilization.

### 1.4 Validation before growth

Interview real buyers and cooks, cost actual recipes, obtain production/payment/delivery advice, and test paid demand under the approved food route. Evaluate the complete payable price. Expand only when safe fulfillment, repeat purchase, acceptable seller earnings, and contribution support it.

Track demand by household, not merely downloads. Do not promise guaranteed seller income or general superiority over restaurant safety/nutrition. Bety's quality promise needs measurable standards.

## 2. Research conclusions and product decisions

### 2.1 What was studied

All 14 Tablya screenshots were reviewed individually. Talabat and Breadfast were studied through first-party app descriptions, terms, and support material; Breadfast's public Chef on Demand experience was also inspected. Exact authenticated mobile flows were not transacted.

Talabat documents search, merchant menus, saved addresses, scheduled ordering, tracking, and reorder. Breadfast documents immediate/scheduled shopping; its scheduling and busy-state help includes older articles. Those are capability references, not verified screen-by-screen reproductions of current mobile builds. [Talabat Egypt listing](https://apps.apple.com/eg/app/talabat-food-grocery-more/id451001072), [Breadfast Egypt listing](https://apps.apple.com/eg/app/breadfast-groceries-and-more/id1288436997).

The [research dossier](./research/competitor-experience-study.md) identifies source dates, observation limits, policy inconsistencies, screenshot IDs, and what remains unverified. No market-share, conversion, reliability, or comparative safety claim is inferred from these references.

### 2.2 Concrete decisions from the Tablya references

- Retain a prominent destination header, kitchen-or-meal search, useful intent shortcuts, visible cook identity, menu categories, configurable meal sheets, quantity controls, and a sticky cart.
- Define every category chip, add action, closed state, favorite, back action, and cart conflict precisely instead of inferring behavior from a screenshot.
- Distinguish preparation duration from arrival estimate, and “cooked” from “ready for this delivery window.”
- Avoid a final-looking total while delivery still depends on an unselected address or unknown fee.
- Keep recurring meal plans separate from one-time checkout until each date, charge, entitlement, and refund is defined.
- Offer pickup only through explicitly eligible premises and a privacy-safe handoff process.
- Put customer support and financial outcomes in Bety's record rather than relying entirely on external conversations.

### 2.3 The original plan's controls retained

Kitchen eligibility; qualified safety ownership; approved recipes; allergen limitations; traceability; conservative capacity; one kitchen per order; verified payment; transparent seller statements; justified holds; fair appeals; and a gated neighborhood rollout remain foundational.

The original's indicative fees and budgets remain assumptions. This blueprint provides a more complete experience specification and additional conditional modes. New commercial or legal decisions must be reconciled with the baseline before implementation.

## 3. Experience model and release boundaries

### 3.1 One shopping context

Every sellable view uses a consistent context:

```text
customer/guest + confirmed destination + fulfillment mode
+ selected meal date/window + preparation type + kitchen/item eligibility
```

An address, date, mode, or preparation-type change invalidates dependent results and prices. Keep the customer's old basket available for review while revalidating; do not silently delete or transform it.

### 3.2 Do not mix different product dimensions

- **Preparation state:** Ready to eat; heat-and-eat if separately approved; finish-at-home only after a distinct safety program.
- **Arrival mode:** Scheduled delivery; express only where currently eligible; approved pickup later.
- **Meal category:** Poultry, vegetables, rice dishes, stews, baked meals, desserts, and other reviewed categories.
- **Portion format:** Individual, measured tray, family bundle, or an explicitly defined size.
- **Merchandising tag:** Offers, new kitchen, popular, vegetarian ingredients, or another substantiated descriptor.
- **Commitment:** One-time meal, finite multi-date plan, or optional future service membership.

“Healthy” cannot stand in for a medical diet or verified nutritional claim. A product may have several tags, but its safety and fulfillment classifications are explicit.

### 3.3 Release definitions

**M0 — Validation:** Interviews, prototypes, approved controlled food trials, real costing, and partner feasibility.

**M1 — First customer release:** Scheduled ready-to-eat meals, one kitchen/window per order, reviewed supply, complete pricing, approved electronic payment, controlled COD if reconciliation is ready, cook production, support/refunds, tracking events, and settlement.

**M2 — Repeat and logistics improvement:** Conditional express supply, richer seller tools, saved baskets, structured paid-change support where feasible, and approved commercial-premises pickup.

**M3 — Additional products:** Finite meal bundles, separately validated finish-at-home products, and catering requests. Each feature remains off until its relevant acceptance scenarios pass.

Home chef visits, an unrestricted wallet, lending, multi-kitchen combined delivery, broad national coverage, and unrelated grocery/financial services are outside this plan's first product.

### 3.4 Roles and navigation

Customer primary tabs: **Home**, **Orders**, **Account**. Search lives prominently within Home, with global and scoped results. The sticky cart is separate from tab navigation and reserves its own safe layout space.

Cook primary areas: **Today**, **Menu & availability**, **Orders**, **Earnings**, **Help/account**. Use role switching only where one authenticated person legitimately holds both customer and seller roles; never infer permission from a visible switch.

Courier jobs and admin workspaces are separate permission-scoped experiences. A partner courier tool is acceptable if its events are reconciled into Bety.

## 4. F01 — Arrival, identity, and returning to intent

**Screens:** C01 launch/deep-link resolution; C02 language/welcome; C03 sign-in/verification.

**Reference:** Talabat's documented account/order journey; Bety-specific guest and recovery design.

**Release:** M1.

Allow guest browsing with an approximate chosen area, then request the information needed for a binding checkout. Authentication is required before order/payment commitment and account-linked actions that need persistence.

Use phone verification as the proposed primary identity flow, with a provider-confirmed OTP method, rate limits, clear resend rules, and a support recovery route. A password is optional only if a separately designed credential lifecycle justifies it; copying a password menu from Tablya is not a reason to add one.

When sign-in interrupts an action, preserve `return_to` intent, basket, selected dish options, and shopping context. Return the customer to the action after verification, then revalidate eligibility and price. Do not leave them at a generic home screen or charge an old quote automatically.

Deep links resolve to a meal, kitchen, collection, order, plan, or support case. Check authorization and current availability. Deleted meals show an understandable unavailable state with safe alternatives; private order links require the correct account and do not reveal order data in link previews.

An app update may require reauthentication. Preserve recoverable local drafts while keeping server-side financial/order records authoritative. Handle expired codes, multiple devices, recycled phone-number risks, locked accounts, and interrupted verification in the edge catalog.

**Acceptance:** A customer opening a shared meal link can choose a configuration, authenticate, and return with that selection intact; no stock or price is trusted until refreshed.

## 5. F02 — Address, serviceability, and location changes

**Screens:** C04 destination sheet; C05 search/map; C06 address details/book; C07 basket impact preview.

**Reference:** T02; Talabat's documented address-dependent supply.

**Release:** M1.

### 5.1 Address selection

Destination sheet choices: current saved address, another saved address, search manually, or use current location. Request location permission only after the customer chooses the GPS action. Manual search must remain usable when permission is denied or inaccurate.

Map selection produces an approximate destination. Delivery confirmation requires building, floor, apartment where relevant, a useful landmark/access note, and a reachable recipient. Clearly distinguish the phone's current location from the delivery destination.

An address object stores a confirmed pin, normalized locality, delivery details, validation status, and version. The backend performs polygon/route-based serviceability checks. Reverse geocoding text alone cannot determine whether a building can be served.

### 5.2 Changing an address while shopping

Preview which basket lines, kitchens, delivery fees, and slots change. Offer: keep the current destination; apply the new one and review affected lines; or save the new address for later. Preserve the former basket as a draft when practical.

Once an order is confirmed, updating the address book changes future defaults only. The active order uses its immutable address snapshot. A change request is handled under F14 and must not redirect a courier without approval.

### 5.3 No service and ambiguous locations

Show an honest unsupported-area state with a manually editable pin and an optional consent-based area waitlist. Do not let the customer pay for an unserviceable destination. Validate unusual gates, compounds, rural descriptions, and inaccessible roads through the operational model.

**Bety edge:** Reliable destination editing even when a user browses away from home; location is confirmed intent rather than a permanently locked first GPS result.

## 6. F03 — Meal date, delivery window, and shopping intent

**Screens:** C08 date/window picker and intent selector.

**Reference:** T01/T06 preparation/time intents; Breadfast's documented scheduling.

**Release:** Scheduled M1; express M2.

Offer a small clear choice such as **Plan a meal** and, only where eligible, **Available sooner**. Do not open an empty express collection merely for parity. Show the earliest real option when immediate supply is unavailable.

The selected day/window remains visible in the home header, kitchen page, meal sheet, cart, confirmation, and order detail. Use absolute date and local weekday alongside “today/tomorrow” in confirmation so midnight or backgrounding cannot create ambiguity.

For scheduled meals, store an order cutoff, free-cancellation boundary, planned production start, pickup window, and delivery window. The example baseline is previous-day 21:00 cutoff for next-day lunch; actual slot configuration remains a pilot decision.

Express eligibility requires an approved recipe/batch, known sellable quantity, valid holding life, kitchen readiness, courier capacity, serviceable route, and a credible total arrival range. A cook's one-hour preparation estimate does not establish one-hour delivery.

When the current slot fills, show the next valid slot and the consequences for the basket. Never shift a paid order to tomorrow because today's slot closed.

**Acceptance:** A customer can state the meal's actual day and arrival window before adding it. Changing date causes availability and promotions to refresh visibly.

## 7. F04 — Home, navigation, and merchandising

**Screens:** C09 home; C10 collection landing.

**Reference:** T01/T11/T12 plus documented competitor discovery capabilities.

**Release:** M1.

### 7.1 Proposed home hierarchy

1. Confirmed delivery destination and meal date/window.
2. Search entry: «بتدور على أكلة ولا مطبخ؟».
3. Active-order reminder, when an order needs attention.
4. A small number of useful intents: individual meals, family portions, today's available supply, future menu, and offers.
5. Reorder/favorite-cook shortcuts for returning customers.
6. Serviceable kitchen groups and meal recommendations with seller identity.
7. New assessed cooks or seasonal collections with clear qualification.

Keep campaigns below critical location/order information. A marketing carousel must not move controls unexpectedly, hijack focus, or claim a price/ETA that does not apply to the selected variant and address.

### 7.2 Reusable cards

A kitchen card shows public name/photo/logo, coarse area, cuisine/style, relevant review count or new state, next valid window, and a truthful fee/ETA preview. Assessment badges link to an explanation.

A meal card shows kitchen, actual photo, measured portion, starting price when variants differ, preparation-state label, relevant slot availability, and an add/configure action. Truncate descriptions safely while keeping portion, price, and required-choice hints visible.

### 7.3 Ranking

Eligibility and relevance come before merchandising. Use serviceability, chosen slot, meal match, reliability, verified feedback, and fair new-cook exposure. Label paid placement. Do not rank unapproved supply or use an unsupported medical suitability score.

Reserve bottom content padding for both tab navigation and sticky cart. A keyboard, accessibility font size, or system inset cannot hide the checkout action or a critical message.

## 8. F05 — Search and relevant discovery

**Screens:** C11 search entry/results; C12 scoped kitchen search.

**Reference:** T01/T06/T07 and Talabat's documented search/filter capability.

**Release:** M1.

Global search covers reviewed kitchen names, dishes, categories, ingredients suitable for ordinary discovery, and known aliases. Suggest both kitchens and meals, clearly separated and still filtered by destination/date.

Support Egyptian Arabic spelling variants, common English/transliterated dish names, punctuation, and reasonable typo tolerance. Normalize for retrieval while preserving the cook's actual displayed name. A broad ingredient match cannot certify absence of allergens or medical suitability.

Within a kitchen, scope search to that menu. A results page must state its scope and offer an explicit return to all kitchens. Retain query, selected date, sort/filter state, and list position when a product sheet closes.

Distinguish no matching phrase, no serviceable result, no result in this slot, and offline/failed search. Offer the relevant recovery: edit query, clear a restrictive filter, choose another date, or retry. Avoid presenting a network error as “no kitchens.”

Use debounced queries and cancel or version responses so a slower old query cannot overwrite a newer one. A card's add action uses current item identity and availability, not the results index.

**Acceptance:** Searching «مكرونة» and a known transliteration can find a published matching dish without losing seller, portion, or selected-day context.

## 9. F06 — Categories, filters, sorting, and collections

**Screens:** C13 category listing; C14 filter/sort sheet.

**Reference:** T06/T07 and T01's intent tiles.

**Release:** M1, with later modes hidden until eligible.

Use distinct controls for meal categories, portion format, selected arrival window, and merchandising. Show active-filter chips and a clear reset action. Counts represent the filtered serviceable result set and are refreshed with context changes.

Proposed sorting: relevance, earliest available arrival, food price for a comparable displayed unit, verified rating with count, and proximity. Explain a “from” price; do not compare a 250 g variant with a family tray as though they were equal portions.

Nearest is not automatically fastest. Straight-line proximity cannot replace route and readiness constraints. If kitchen privacy requires approximate distance, label the approximation and avoid exposing a precise household pin through the API.

Category results may group meal carousels by kitchen, as in the Tablya references, but ensure the layout supports direct access to each product and a clear “view menu” action. A grid/list preference can be deferred; consistent accessible behavior matters more than multiple layouts.

For “offers,” display eligible sale price, original valid comparison price, variant scope, and terms. For “healthy,” use approved factual attributes such as vegetarian ingredients or measured portion; do not imply a treatment recommendation.

**Acceptance:** Applying a filter cannot expose unavailable items as purchasable, and changing sorting cannot silently reset the destination or delivery day.

## 10. F07 — Kitchen and cook profile

**Screens:** C15 kitchen overview/menu; C16 kitchen information/reviews.

**Reference:** T03/T04/T08/T09.

**Release:** M1.

### 10.1 Header and identity

Display public kitchen name, optional cook portrait/story with permission, coarse neighborhood, verified-order rating/count or new state, specialties, next valid arrival window, relevant minimum basket/fees, and assessment scope/date. Seller disclosures follow the approved legal model.

An expandable “about this kitchen” area explains style, included operating standards, allergen/cross-contact limitations, current preparation premises eligibility, and support. Do not publish identity documents, full household coordinates, private family information, or unsupported safety claims.

### 10.2 Menu behavior

Use a sticky compact header after the hero scrolls away, visible menu-section chips, clear section headings, and accessible product rows. Chip taps jump to a section; scrolling updates the active chip; closing a meal sheet restores the previous list position.

Meal availability belongs to a date/window. Different groups can include available now, next-day preorder, or unavailable in the chosen context, but never merge them without labels. “Popular” is based on genuine defined activity; sponsored items are labeled separately.

### 10.3 Explicit availability states

- **Open for chosen slot:** Purchasable reviewed items are visible.
- **Closed now, future ordering available:** Offer a valid future date and revalidate the menu.
- **Busy/capacity full:** Display the next genuine slot.
- **Sold out:** Disable unavailable lines and show eligible alternatives.
- **Not serving this address:** Offer a destination change without pretending a purchase is possible.
- **Paused/eligibility or safety hold:** Prevent new commitment; route existing orders to operations.

**Acceptance:** Every visible purchase control either completes a valid configuration/add action or presents an explicit resolution path. A generic closed badge cannot coexist with an unexplained purchase promise.

## 11. F08 — Meal details, variants, and add to cart

**Screens:** C17 meal sheet/detail; C18 choice validation.

**Reference:** T05/T09.

**Release:** M1.

### 11.1 Meal information hierarchy

Show the actual dish image, kitchen, preparation-state label, included components, measured portion, approximate servings, ingredients/allergens, cross-contact limitations, chosen-day availability, and exact arrival promise. Provide readable storage/reheating guidance where applicable.

Separate size/weight variants from modifiers. A 500 g package is a variant with its own price and stock. A sauce choice may be a required modifier. Extra rice may be an optional add-on. Quantity means the number of complete configured units.

For every option group define its minimum/maximum choices, defaults if any, price change, ingredient/allergen effect, availability, and kitchen production implications. Never encode a safety-relevant protein or ingredient choice solely in free text.

### 11.2 Add behavior

Quick add succeeds only for an unambiguous item with no unresolved required choices. Otherwise open the meal sheet, highlight the first required choice, and disable the commitment action until valid. A single available option may be visibly selected, but must remain understandable.

Display unit price, quantity, and calculated line total. Use integer minor units and server pricing. If a discount applies only to a size, show it for that size; do not suggest every size has the same saving.

Identical meal version, variant, modifiers, and slot may merge into one cart line. Different choices create separate editable lines. Editing a line updates only that configuration and rechecks capacity.

Closing the sheet without adding leaves the basket unchanged. Returning from authentication restores the draft choices. A stale price/stock response explains the change and requires a fresh customer decision.

### 11.3 Special notes

Allow a short optional preference note for supported non-contractual requests. Clearly state that notes cannot substitute for variant choices or change allergen guarantees. Customer allergy questions route to approved factual information and support; unsupported safety requests are declined.

**Acceptance:** The cook receives the same structured variant/option IDs that the customer reviewed, with matching description, price, recipe version, and ingredient disclosure.

## 12. F09 — Cart, saved baskets, and kitchen conflicts

**Screens:** C19 cart; C20 line edit; C21 conflict/restore sheet.

**Reference:** T03–T09 persistent cart; T13 cart controls.

**Release:** Core M1; multiple saved drafts M2.

### 12.1 One active checkout

One active cart belongs to one kitchen, one meal date/window, one preparation/fulfillment arrangement, and one destination context. The sticky bar shows that kitchen, quantity interpretation, food subtotal or validated total label, and a clear view-cart action.

Browsing other kitchens does not change the cart. When adding from another kitchen, show the current kitchen and the proposed new one. Offer keep current cart, or save/replace after confirmation. The MVP may preserve one recoverable previous draft without supporting simultaneous multi-kitchen checkout.

Do not infer multi-kitchen ordering from a sticky cart remaining visible on another kitchen's screen. An actual multi-seller order would need separate commitments, deliveries, refunds, and settlement; it is deferred.

### 12.2 Cart controls

Each line shows meal, seller, variant/options, portion, quantity, price and any discount. Quantity changes revalidate stock. Reducing the last unit requests removal or performs an undoable removal with an accessible notice. Clear-cart requires confirmation and can preserve a short-lived local undo draft.

“Add more” returns to the originating menu, category, and scroll position under the same context. A recommendation cannot silently introduce another cook, a different date, or an incompatible preparation type.

### 12.3 Persistence and expiry

Persist drafts across app restarts with a last-updated timestamp. On return, refresh prices, menu versions, eligibility, fees, stock, and cutoff. Draft carts do not reserve portions. Explain expired/unavailable lines and offer removal, a future slot, or an eligible replacement.

Guest-to-account merge is explicit if both contain a basket. Do not combine kitchens or quantities invisibly. A saved basket is a template, never a promise of price or supply.

**Acceptance:** A basket survives interruption, but checkout cannot rely on stale availability or silently replace customer choices.

## 13. F10 — Prices, offers, and complete totals

**Screens:** C22 price breakdown/promo entry.

**Reference:** T13/T14 and Talabat's documented fee disclosure; Bety's own pricing rules.

**Release:** M1.

### 13.1 Quote composition

```text
Food by configured line
− customer food discounts, with sponsor allocation recorded
+ packaging where separately and lawfully charged
+ delivery
+ service fee
+ other explicitly enabled and approved charges
+ applicable tax treatment
= exact total payable
```

Actual production checkout must show the legally required tax-inclusive or otherwise required final presentation. Financial examples in this blueprint exclude tax adjustments unless explicitly stated.

If the destination/slot is missing, label the amount **food subtotal**, not final total. The action becomes “Choose address/time” or “Continue to delivery details,” not an unconditional “Pay.” A kitchen-determined delivery price must be resolved before the customer authorizes payment.

Minimum food spend, delivery fees, service fees, optional cutlery, small-basket charges if ever enabled, and COD costs must be explained before commitment. Avoid adding every possible fee merely because a competitor has one; begin with the smallest understandable structure that supports operations.

### 13.2 Discounts

Store eligibility by account, kitchen, item/variant, date/window, payment method, threshold, usage cap, stacking rule, sponsor, and effective time. “First order” is defined by eligible actual order history, with fair household-abuse review rather than automatic punishment of everyone at one address.

Show valid comparison prices and the applicable size. Coupon application recalculates the full quote. Removing an item, changing address, choosing pickup, changing payment method, or refunding an item may affect eligibility; show the effect before commitment.

A Bety-funded offer preserves the seller's agreed proceeds under the recorded commission base. Seller-funded or shared offers require seller consent and visible net earnings. Partial refunds allocate the original discount rather than returning undiscounted cash or silently clawing back unrelated promotions.

### 13.3 Quote expiry

A quote has a version, expiration, policy versions, and all inputs needed to reproduce it. It is separate from an inventory reservation. A displayed quote does not guarantee stock until the order workflow reserves it.

If a quote expires, recalculate and display material differences. Do not raise an amount after payment authorization, switch a funding source, or create a second charge without a new informed commitment.

## 14. F11 — Checkout and schedule commitment

**Screens:** C23 checkout/review; C24 slot re-selection; C25 recipient instructions.

**Reference:** T13/T14 and Breadfast's documented slot selection.

**Release:** M1.

Use a clear review screen with editable destination, named recipient/contact, kitchen, date/window, meal lines, fulfillment mode, payment method, item notes, delivery notes, offer, complete total, and cancellation cutoff. Keep the primary action and exact amount visible without obscuring content.

### 14.1 Suggested checkout sequence

1. Confirm serviceable address and recipient.
2. Confirm the selected date/window and kitchen availability.
3. Review configured lines, portions, ingredient/allergen disclosures, and supported requests.
4. Apply any eligible promotion and recalculate the full price.
5. Choose an available payment method and display the relevant policy summary.
6. Atomically reserve portions plus kitchen/slot/delivery capacity for the displayed short payment period.
7. Initiate the approved payment/COD workflow with an idempotent order commitment.
8. Show verified confirmation or an honest payment-checking state.

The backend rechecks eligibility at commitment even if every screen looked valid. A capacity failure returns a useful next option without charging an impossible order.

### 14.2 Recipient and delivery instructions

Provide structured access details and a bounded optional note. Gift/other-recipient delivery is a later controlled option requiring a consented reachable recipient and clear communication routing. Do not enroll a recipient in marketing because someone else sent them a meal.

Notes cannot change money, delivery zone, payment method, allergen handling, or kitchen commitments. Separate meal preferences from door/access instructions so only appropriate actors see them.

### 14.3 Reservation rules

Use a proposed maximum 10-minute payment reservation, shortened by the ordering cutoff. Show server-derived expiry. Confirming moves reservation to committed capacity transactionally; expiry releases it once.

When the app resumes, retrieve the current order/payment state before suggesting a retry. Releasing a reservation does not prove a bank transaction failed; F12 handles late results.

**Acceptance:** The customer can review every material commitment before paying, and the receipt matches the accepted quote and delivery context.

## 15. F12 — Payment, confirmation, and uncertainty

**Screens:** C26 provider payment; C27 checking/result; C28 confirmation/receipt.

**Reference:** Competitors' documented payment capabilities; Bety-specific integrity design.

**Release:** M1.

### 15.1 Supported payment arrangement

Use an approved bank/provider marketplace collection and payout structure. Enable only payment methods available under the actual contract. Card/wallet tokenization, authentication, capture/authorization, refunds, fees, and settlement differ by provider; final integration follows those authoritative contracts.

Support must never request a card photo, raw card number, bank password, or payment OTP. A transfer screenshot is not proof of cleared funds.

### 15.2 Truthful states

- **Awaiting payment:** Order exists with a live reservation and no verified commitment.
- **Checking payment:** Provider outcome is unresolved; show an order reference and safe refresh/support action.
- **Confirmed:** Server verified payment or eligible COD and valid stock/slot commitment.
- **Not accepted:** Payment failed/expired or the order could not legally/safely commit.
- **Void/refund pending:** Funds moved or were held but no valid order can be fulfilled; expose resolution progress.

A provider return URL or client “success” screen is not final payment evidence. Verify signatures, amounts, currency, account/order references, and event uniqueness server-side.

### 15.3 Failure recovery

Reuse the same order/attempt for double taps and retries. If the provider times out, show checking and reconcile; do not tell the customer to pay again while the first outcome remains uncertain.

If success arrives after reservation expiry, revalidate the original accepted quote, kitchen, stock, slot, and cutoff. Confirm once only if valid. Otherwise void/refund using the approved provider method and explain that the order was not accepted. Never silently overbook or move the meal date.

Distinguish a released authorization from a completed refund where the provider uses holds. Show provider-based time expectations and references; do not invent a universal bank timeframe.

### 15.4 COD

Enable COD only with verified customer/contact, eligibility and amount caps, courier cash exposure limits, proof of collection, remittance, daily reconciliation, and a workable lawful refund method. “Confirmed COD” is an order commitment, not a captured electronic payment.

**Acceptance:** A customer can leave and reopen the app after a payment interruption, find the existing attempt, and obtain the correct final outcome without a duplicate charge.

## 16. F13 — Active orders and truthful tracking

**Screens:** C29 orders list; C30 active-order detail/tracking; C31 receipt/history.

**Reference:** Talabat's documented tracking and order history; Tablya's orders navigation.

**Release:** M1.

Order history includes completed, canceled, failed, checking-payment, and refund-related records with understandable labels. A failed transaction with a financial consequence must remain discoverable even if it never became a meal order.

### 16.1 Customer sequence

```text
Confirmed for a date/window → Scheduled → Preparing → Packed/ready
→ Courier collected → Arriving → Delivered
```

Keep payment, fulfillment, refund, and settlement as separate state domains. Delivered plus partially refunded is a valid combination; refunding does not erase delivery evidence.

Show kitchen, accepted portions/options, recipient/address snapshot, date/window, exact paid amount, policy actions, support, and status update time. Multiple active orders remain independently accessible.

Use live courier location only from authorized reliable data while useful. Otherwise show recorded stage and last update. A map icon is not proof of delivery. Stop sharing courier details when access is no longer necessary.

### 16.2 Delay and handoff

Proactively notify when the promise is at risk, explain a realistic update, and offer the applicable support/remedy. Do not repeatedly push the ETA forward while suppressing a known failed delivery.

Use a delivery PIN or approved alternative at actual handoff. Never request the completion PIN at preparation or pickup. A disputed “delivered” state opens an urgent case and preserves custody evidence.

An early arrival outside a scheduled window is also a service exception. The customer agreed to a window and need not be available hours earlier. Food-safety limits still govern any attempted recovery.

**Acceptance:** Status reflects actual authorized events, and the customer can reach help from every non-terminal stage and relevant financial record.

## 17. F14 — Changes and cancellation

**Screens:** C32 change request; C33 cancellation preview/result.

**Reference:** Competitors' documented state-related cancellation; Bety's own proposed policies.

**Release:** M1 with limited edits; richer safe amendment M2.

### 17.1 Changes before confirmation

Quantity, variant, address, slot, fulfillment mode, and coupon changes create a fresh quote and capacity evaluation. An old payment attempt must be resolved before replacing its commercial commitment.

### 17.2 Changes after confirmation

In M1, allow safe non-commercial delivery-note corrections through authorized support. Material meal/quantity/day/address changes use a reviewed cancel/reorder or an explicit support decision. Show the effect on price, eligibility, preparation, cancellation loss, and refunds before the customer agrees.

Never silently edit an accepted recipe, move an order between cooks, or redirect to an unserviceable address. A cook's ingredient shortage requires informed customer acceptance of an eligible alternative or an appropriate refund.

If a future amendment workflow is introduced, model a versioned change request with acceptance, incremental payment/refund, stock transfer, and rollback if the new commitment fails. Preserve the old order until a valid change is committed.

### 17.3 Cancellation preview

Before free-cancellation cutoff, the proposed customer promise is a full refund. After cutoff, any retention must follow approved pre-disclosed rules, evidenced nonrecoverable cost, and applicable rights. The baseline proposes a maximum 50% food retention before preparation and up to actual food loss after it, subject to legal approval; it does not authorize automatic penalties.

The preview shows amount paid, exact refund, any retained amount/reason, payment destination, expected processing, and appeal. Refund unperformed charges under the applicable approved policy. Customer rights for supplier failure or unsafe/defective food are not treated as change of mind.

Customer retention and seller compensation are separate. Bety budgets any gap between a promised seller commitment and lawful customer recovery. No party can recover the same loss twice.

### 17.4 Race with preparation

Cancellation and production-start events compete against server state transactionally. Use an authoritative timestamp and commitment boundary, not whichever screen rendered last. If the outcome changed during review, refresh the preview and explain it before finalizing.

**Acceptance:** A cancellation cannot both release the last portion for resale and leave the original order active; money, stock, production, and case records reconcile.

## 18. F15 — Support, refunds, and safety reports

**Screens:** C34 help entry; C35 order-linked case/chat; C36 refund detail; C37 urgent safety report.

**Reference:** T10; documented competitor support and issue handling.

**Release:** M1.

### 18.1 Accessible triage

Offer relevant categories and an “another problem” route: payment uncertainty, wrong/missing item, portion issue, late/failed delivery, kitchen unavailable, cancellation, refund, account/privacy, harassment, and food safety. Do not trap an unusual problem inside an irrelevant chatbot category.

Display service hours, current response expectations, and escalation options honestly. Order-linked conversations carry order/line/batch references without making the customer repeat basic details.

WhatsApp or phone may be an assisted fallback if properly operated, but record the case and decisions in Bety. Never imply an external message was delivered/read unless the channel confirms it.

### 18.2 Remedies and refunds

Support can offer safe replacement where feasible and consented, partial/full refund, delivery-fee remedy, or another lawful agreed resolution. Do not force store credit or require a customer to withdraw a complaint.

Refund states: requested, reviewed/approved, provider submitted, processing, succeeded, failed. Show the amount and original method where possible. A provider-submitted refund is not presented as money already received.

Partial item remedies allocate original discounts and taxes/fees correctly. Responsibility for seller/courier deductions is reviewed separately from the urgent customer remedy. Refund totals cannot exceed the remaining refundable captured amount.

### 18.3 Urgent safety

Provide a prominent way to report suspected contamination, undeclared allergen, tampering, or illness. Advise stopping consumption and seeking appropriate urgent medical assistance where needed; support does not diagnose.

Immediately notify the duty safety lead, quarantine relevant stock/batches, stop affected dispatch/sales, identify all related orders, and coordinate required professional/regulatory action. Preserve evidence with restricted access and reopen only after documented correction and review.

Do not require a photo or medical proof as a precondition to taking a credible safety report seriously. Repeated-refund review cannot suppress safety triage.

**Acceptance:** Each case has an owner, status, next update, decision, money reference, and appeal path. A customer can follow the case even when push notifications or external chat fail.

## 19. F16 — Reviews, favorites, and reorder

**Screens:** C38 review; C39 saved kitchens/meals; C40 reorder review.

**Reference:** T03/T05/T10/T11/T12 and documented competitor repeat-order features.

**Release:** M1.

Prompt for reviews after actual fulfillment, separating meal/portion quality, packaging, and delivery where useful. Safety reports go into a private operational case immediately; a star rating alone is not safety triage.

Only genuine eligible order feedback contributes to public ratings. Show count and defined calculation; a new cook has an honest new/unrated state. Moderate abuse, household addresses, phone numbers, and irrelevant personal information while preserving fair criticism and appeals.

Favorites preserve kitchen/meal identity, with an available-next-date state when the chosen day is closed. Follow/notification preferences are separate from a favorite; tapping a heart does not authorize marketing spam or a recurring purchase.

Reorder opens a review of current menu versions, price, stock, date, address, and supported options. Show unavailable lines and alternatives explicitly. An old meal may have changed ingredients/allergens and must not bypass current disclosure.

A reorder can remain same-kitchen only. Adding an old order to an existing cart uses F09's conflict behavior. Never silently duplicate quantities or create a charge from a reorder tap alone.

**Bety edge:** Repeat the useful meal routine with minimal effort while making changed portions, ingredients, date, and price visible before commitment.

### 19.1 Referrals, rewards, and optional tips

Defer monetary rewards until ordinary retention and accounting work. A future referral identifies an inviter/code, clear eligibility, a qualifying fulfilled order, sponsor cost, redemption conditions, expiry, and abuse/appeal handling. Do not grant spendable value for canceled/self-referral transactions or import a cook's private contacts to recruit buyers.

Any points program must distinguish pending, available, redeemed, reversed, and expired value, with an approved liability/accounting model. Show an accessible activity record and disclose any expiry before earning/redeeming. It cannot silently replace a cash/original-method remedy owed to a customer.

Tips, if introduced, are optional and separate from required delivery/service charges. Define recipient, allocation, collection, payout, cancellation/refund treatment, and tax/provider implications before enabling them. Do not preselect a tip, display it as a mandatory courier fee, or count it as platform commission revenue.

These optional capabilities are not part of M1 and are not represented as approved payment services. Add dedicated detailed scenarios and obtain the necessary commercial/provider review before activating them.

## 20. F17/F18 — Account, privacy, notifications, and messaging

**Screens:** C41 account; C42 contact verification; C43 preferences/privacy; C44 communications/case inbox.

**Reference:** T10 and first-party account/support capability descriptions.

**Release:** M1.

### 20.1 Account lifecycle

Allow name, verified phone, preferred language, saved addresses, favorites, payment tokens where supported, help/legal access, marketing choices, logout, data-rights requests, and account deletion.

Phone changes require verification of the new number and a secure recovery/re-verification path. Invalidate compromised sessions and protect active orders. Do not reveal another account's existence through phone lookups.

Explain retention of necessary order, financial, safety, and legal records when deleting an account under the approved policy. Stop optional marketing and remove/anonymize unnecessary profile data. Give a secure support route for unresolved deliveries/refunds rather than erasing access or silently blocking deletion forever.

### 20.2 Notifications

Separate operational messages from optional menu/offer reminders. Request push permission in context and respect OS denial. Orders, payment checking, cases, and refunds remain accessible inside the app.

Important events have deduplication and delivery tracking. Use an approved backup channel for critical operational updates when needed. Avoid sensitive food/health/address details on lock-screen previews.

### 20.3 Customer–cook questions

M1 supports structured pre-order questions and order-linked support-mediated communication, with response expectations. If direct in-app chat is added, preserve moderation/reporting, role access, message timestamps/status, and an auditable commitment path.

Chat cannot change price, ingredients, allergen assurances, payment destination, or delivery date by itself. A meaningful promise becomes a reviewed quote/change request. No response is not acceptance.

Keep private cook contact details and home address restricted. Report harassment easily, allow contact limits without losing access to support, and never ask a cook to reveal family information to reassure a customer.

**Acceptance:** Notification permission denial, lost chat delivery, or a phone change does not create an invisible order, an untraceable financial decision, or unauthorized data access.

## 21. F19 — Finite meal plans and recurring commitments

**Screens:** C45 plan builder/calendar; C46 plan review/payment; C47 plan management/occurrences.

**Reference:** T13's visible weekly/monthly choices; Bety-specific commercial design.

**Release:** M3, after ordinary ordering and seller capacity are reliable.

### 21.1 Three different products

**A one-time order** buys named meals for one date/window.

**A finite meal plan** buys an explicit set of dated meal entitlements. It ends after those occurrences and does not renew by default.

**A service membership** buys defined benefits such as eligible delivery discounts; it does not itself order food. Auto-renewal, if ever introduced, needs separate consent, billing, termination, and payment-retry design.

Use separate models and labels. “Weekly” cannot ambiguously mean seven calendar days, five working lunches, one delivery per week, or indefinite auto-renewal.

### 21.2 Plan-building flow

Select eligible kitchen/plan, specific dates, portions, each date's meal or defined future-menu selection process, delivery window/address, exclusions, and payment. Show every delivery, food subtotal, discount, delivery/service charges, applicable taxes, total commitment, cancellation/skip rules, and end date.

Reserve capacity for every committed occurrence transactionally or through a durable all-or-nothing reservation workflow. If one date is unavailable, show it before charging and let the customer change the plan. Do not accept money for future portions without a credible seller and capacity commitment.

If future menus are not yet known, do not claim an unspecified food purchase is a fixed known meal. Define a separate selection deadline, approved credit/refund treatment, and an explicit customer decision; defer this complexity from the first finite plan.

### 21.3 Illustrative arithmetic

For seven explicitly chosen deliveries at EGP 350 food each, a hypothetical Bety-funded 5% food discount gives:

```text
Food: 7 × 350                                      EGP 2,450.00
Bety-funded food discount at 5%                    EGP   122.50
Delivery: 7 × 35                                   EGP   245.00
Service: 7 × 10                                    EGP    70.00
Customer total before tax adjustment               EGP 2,642.50
```

This is an assumption, not Tablya's verified calculation or a launch price. Under an unchanged 20% commission on undiscounted food, seller proceeds are EGP 1,960 across the seven fulfilled occurrences, before applicable seller-specific adjustments. Bety bears the EGP 122.50 promotion.

Allocate the food discount as EGP 17.50 per occurrence. An eligible full cancellation of one unprepared occurrence returns its EGP 332.50 discounted food plus the EGP 35 delivery and EGP 10 service under this example: EGP 377.50 before tax adjustments. Do not retroactively reprice completed meals unless a specific lawful, transparent rule was accepted; the recommended pilot has no surprise discount clawback.

### 21.4 Management and exceptions

Show upcoming/delivered/canceled occurrences, remaining entitlement, actual refund amount, seller, meal, address, window, and next deadline. Skip/reschedule requests check new capacity and price effects before acceptance. Original records remain linked to replacements.

Handle cook leave, illness, approval lapse, unavailable meals, holidays, missed delivery, customer travel, address changes, payment failure, and partial refunds at occurrence level. No automatic substitute cook or allergen-bearing meal change.

Release seller earnings per fulfilled occurrence under the settlement cycle. Future prepaid obligations remain liabilities under the approved accounting/fund-flow treatment; do not treat them as immediately spendable operating profit.

**Acceptance:** Every charged entitlement maps to a dated fulfillment or a visible unresolved/refunded obligation, and the customer can stop future eligible occurrences without a support guessing exercise.

## 22. F20/F21 — Pickup, requests, catering, and finish-at-home

### 22.1 F20 — Approved pickup

**Screens:** C48 pickup location/window; C49 collection code.

**Reference:** T13 and Talabat's documented pickup capability.

**Release:** M2 only at approved customer-facing premises.

Default household kitchens to platform delivery. Offer pickup only when premises, access, seller consent, safety, legal disclosures, and operating hours permit it. A public pickup option is not a reason to expose a private family home.

Changing from delivery to pickup before confirmation recalculates slot, fees, promotions, packaging, and instructions. Show a verified collection location, time/window, access directions, order code, and support. Use a pickup code at actual handoff.

Define late arrival, no-show, collection by another authorized adult, code failure, and safe holding expiry. Prepared food never remains available indefinitely because the customer paid. Refund and seller-loss treatment follow the approved disclosed policy, not an automatic blanket forfeiture.

### 22.2 F21 — Structured meal requests

**Screens:** C50 request form; C51 quote review.

**Release:** M3 for controlled custom requests.

Request fields: date/window, serviceable destination, people/portion estimate, requested dishes, budget range, factual ingredient restrictions, and notes. Display “request” rather than “confirmed order.” No charge until a reviewed seller, exact menu, portions, ingredients/allergens, price, delivery, and cancellation terms are accepted.

A cook can propose or decline through a bounded response process. Quotes expire, are capacity-checked, and preserve the accepted version. Chat suggestions alone are not a purchase commitment.

### 22.3 Catering

Use a separate quote/deposit workflow with event date, guest count, approved menu, production capacity, delivery setup, packaging/service scope, payment milestones, cancellation exposure, and contingency. Allergen and temperature controls still apply.

Do not reuse an individual-meal basket and merely multiply quantities for a large event. Validate kitchen/courier throughput and safe holding at the destination. Home chef visits remain a different service outside this product.

### 22.4 Finish-at-home and chilled products

Tablya's category tile establishes a visible shopping intent, not the safety or contents of its products. Bety introduces such items only after a separate approved process for preparation state, cold chain where relevant, packaging, labeling, shelf life, cooking/storage instructions, and transport.

Make raw, partially prepared, fully cooked chilled, and ready-to-eat states unmistakable. Avoid mixed-mode baskets initially. A customer must not mistake a product requiring cooking for dinner ready to eat. Do not add infant food, therapeutic diets, or guaranteed allergen-free production without separate qualified validation.

**Acceptance:** Each later mode has a truthful promise, valid production route, complete quote, matching operations, and passing edge cases before it is discoverable.

## 23. F22/F23 — Cook onboarding, menus, and availability

### 23.1 F22 — Assisted onboarding

**Screens:** K01 application/status; K02 documents; K03 assessment/remediation; K04 training/trial; K05 commercial/payout setup.

**Release:** M1.

Use short Egyptian Arabic steps and optional assisted entry. Collect adult contracting eligibility, identity, legal seller details as required, production location/permissions, food-handler information where required, equipment, capacities, specialties, available days, and verified payout setup.

Stages: interested, submitted, identity review, production eligibility, kitchen assessment, remediation if needed, training, menu/costing review, controlled trial, commercial agreement, payout verification, and approved within conditions.

Each stage has an owner, evidence, reason, next action, and review date. Identity approval is not kitchen approval; a beautiful dish photo is not a food-safety assessment. Required document expiry blocks affected future commitments and exposes existing orders for resolution.

Provide understandable rejection/remediation reasons and an appeal. Do not pressure a mother to disclose children, marital circumstances, family photos, or private household details irrelevant to operating eligibility.

### 23.2 F23 — Catalog and earning-aware publishing

**Screens:** K06 profile; K07 meal editor/review; K08 cost calculator; K09 calendar/capacity.

**Release:** M1.

Create versioned recipes, structured variants/modifiers, measured portions, ingredient/allergen declarations, actual photos, prices, preparation/holding guidance, and sellable slots. New critical ingredients or process changes require review before sale.

The cook's costing tool includes ingredients, packaging, utilities, shopping/preparation/packing/cleanup labor, waste, commission, promotion funding, and applicable tax effects. Show expected net proceeds and contribution before a meal is published.

Treat published slot inventory as a firm commitment up to its approved cap. In M1, valid paid/eligible-COD orders auto-confirm within that inventory; do not force customers into an indefinite paid acceptance wait. Custom requests follow F21 instead.

Availability controls include working days, individual meal portions, combined kitchen resource limits, pickup/dispatch throughput, and delivery slot capacity. A daily oven or labor constraint cannot be independently reused by every dish.

Pausing stops new supply while showing remaining confirmed commitments. Reducing quantities below existing commitments raises an operations case. No invisible cancellation or arbitrary reassignment to another cook.

**Acceptance:** A cook knows exactly what has been committed, when to produce it, what constraints apply, and what she is expected to earn.

## 24. F24/F25 — Production, packing, couriers, and handoff

### 24.1 F24 — Today and production board

**Screens:** K10 today/batches; K11 required checks/packing; K12 pickup handoff; K13 incident/help.

**Release:** M1.

Aggregate production by approved recipe version, batch, portion, modifier, and delivery window. Generate package identifiers/labels tied to order and batch. Present a clear sequence with required records and exception reporting.

Qualified staff define hygiene practices, supplier/ingredient traceability, critical measurements, cooking/holding/transport limits, illness reporting, and corrective actions for the actual foods and premises. This blueprint does not substitute generic app checkboxes for a validated food-safety process.

Before preparation, verify current kitchen eligibility, staffing/health, water/power, equipment, ingredients, and quantity plan. During production, follow approved separation and handling. Before readiness, complete required checks, label and seal, and confirm remaining safe fulfillment allowance.

Critical failure blocks dispatch. The cook can report illness, power loss, ingredient shortage, or unsafe conditions without pressure to continue. Operations resolves customer commitments, backup supply, and appropriate refunds.

### 24.2 F25 — Courier experience

**Screens:** D01 assigned jobs; D02 pickup verification; D03 route/contact; D04 handoff; D05 failed-delivery/cash report.

**Release:** M1 through an approved partner tool or secure lightweight interface.

Courier assignment exposes only necessary job details. Reveal the exact private pickup location only to an authorized assigned courier at the necessary time. Reassignment revokes the former courier's access and pickup token.

At pickup, verify cook/courier/order code, package count/IDs, seals, relevant handling requirements, and custody transfer. A courier cannot open packages or change meal contents. Use validated hot/cold transport and route limits.

At destination, verify order/recipient, complete actual handoff, collect only the authorized COD amount if relevant, and record proportionate proof. No photos of private interiors or identity documents. Avoid unattended delivery in the first release.

If the customer is unavailable, attempt contact under a published procedure while maintaining safe conditions. A proposed maximum ten-minute wait is shortened by safety limits. Support determines a safe feasible recovery; no automatic resale of returned/uncertain-custody food.

### 24.3 Responsibility for delays

Record whether the delay occurred in production, packing, dispatch, travel, access, or handoff. Resolve the customer's immediate problem and assess contractual responsibility afterward. Do not penalize a cook's meal rating for a courier delay or force a cook to absorb Bety overselling.

**Acceptance:** Every collected package has a traceable batch, authorized custody path, truthful delivery outcome, and a recorded disposition when fulfillment fails.

## 25. F26/F27 — Settlement, administration, and safety control

### 25.1 F26 — Seller statements and payout

**Screens:** K14 earnings/order statement; K15 payout details; O01 reconciliation; O02 payout approval.

**Release:** M1.

Show sales, accepted commission base, sponsor-funded discounts, valid refunds/adjustments, taxes/withholding where applicable, seller payable, any specific hold, and payout reference/status. Separate sold, eligible, scheduled, and paid amounts.

Use a published weekly payout cycle subject to actual provider settlement and banking days. Holds require amount, reason, owner, next review, and appeal. Do not freeze unrelated earnings indefinitely because of a single complaint.

Reconcile order ledger, payment attempts, provider/bank settlements, COD collections/remittances, refunds, chargebacks, seller liabilities, and payout runs. Immutable financial entries use correcting reversals and unique references.

Payout-detail changes require secure re-verification, trusted-channel notice, approved cooling/review controls, and extra scrutiny for the first new-destination payout. A chat message cannot redirect funds.

### 25.2 F27 — Admin workspaces

**Screens:** O03 live operations; O04 seller assessment; O05 catalog/configuration; O06 support/cases; O07 safety/traceability; O08 access/audit; O09 reporting.

**Release:** M1.

Live operations groups commitments by date, kitchen, batch, courier, risk, and unresolved payment/delivery state. Support sees relevant order/context and authorized remedy actions. Safety staff can quarantine batches and stop a kitchen immediately. Finance has independent reconciliation/payout capabilities.

Configure fees, zones, cutoffs, eligibility, promotion funding, and capacity with version/effective date. Existing accepted orders keep their commercial snapshots; a safety-related change can still require containment.

Use granular permissions, audit trails, and dual review for high-impact financial releases and serious-incident reopening. During a small pilot, explicitly document founder review where complete role separation is impractical.

### 25.3 Safety control and recall capability

Trace ingredient/supplier lot to approved location, recipe version, batch, checks, package, order, courier, recipient, and complaint. A refund does not remove a customer from an affected-batch list.

A credible serious concern triggers immediate safety triage, relevant stop-sale/dispatch, customer protection, professional assessment, and required reporting. Define actual authority contacts and deadlines with qualified Egyptian advice before operating. Reopen only after corrective evidence and authorized review.

### 25.4 Legal workstream retained

Resolve actual premises/activity permission, seller/business classification, food requirements, consumer terms, tax/invoices, insurance, worker/courier arrangements, payment collection/payout authority, privacy permissions, and cross-border vendors. The [baseline regulatory workstream](./bety-business-and-experience-plan.md#17-egyptian-legal-and-regulatory-workstream) remains applicable; no new exemption is inferred from competitor onboarding or marketing language.

If residential production is not approved, evaluate an eligible shared-kitchen route and recost it. A Bety-operated kitchen or chef visit would materially change responsibilities and economics.

## 26. F28 — Accessibility, interruption, and recovery

**Applies to:** Every customer, cook, courier, and admin screen.

**Release:** M1 and every later capability.

Support proper RTL reading/focus order, mixed Arabic/English addresses, clear EGP amounts, accessible touch controls, dynamic type, screen-reader labels, contrast, and visible validation. Weight, quantity, price, discount, and delivery day cannot be conveyed only by color or an icon.

Bottom sheets preserve drafts and context, manage focus, support back/close predictably, and keep required choices accessible above the keyboard. Horizontal carousels remain navigable with assistive technology. Essential actions do not disappear under tab bars, sticky carts, or system insets.

Design distinct loading, genuinely empty, unavailable, offline, unauthorized, expired, pending, and failed states. An offline home can show clearly stale cached content, but cannot claim current stock or a binding final quote.

After process death, network loss, backgrounding, session expiry, or app upgrade, recover drafts and retrieve authoritative orders. Unsynced cook/courier actions remain visibly pending; a local ready tap cannot dispatch a courier before the server accepts it.

Use UTC timestamps plus timezone-aware business rules for Africa/Cairo. Test midnight, daylight-saving changes, holidays, missed schedules, and clients with incorrect clocks.

An API outage should allow a controlled sales pause while preserving support, financial reconciliation, and operations recovery. Never continue taking blind payments just to keep a checkout button active.

**Acceptance:** Critical flows remain understandable on representative lower-cost phones, slow connections, denied permissions, and accessible layouts, with no hidden duplicate commitment.

## 27. Commercial model and sustainable economics

### 27.1 Revenue and seller value

Start with a clear food commission, transparent delivery charge, and only a justified visible service fee. The baseline's proposed commission testing range of 15–22% is a hypothesis; 20% is used below for continuity. Basic access should not depend on large upfront cook listing charges.

Bety delivers value through demand, presentation, coordination, safety standards, support, and accurate payment. Do not rely on broad exclusivity, seller debt, customer-data resale, or complex financial products to make the model work.

### 27.2 Illustrative one-order economics

All values are EGP assumptions, before applicable tax adjustments and costs not listed:

```text
Food subtotal                                       350
Delivery charged to customer                         35
Service fee                                          10
Customer payable before tax adjustment               395

Commission at 20%                                     70
Seller proceeds before seller-specific adjustments   280
Platform commission + delivery + service inflow      115
Courier cost                                         45
Payment allowance                                    10
Variable support                                      8
Expected refund/claim allowance                       7
Bety promotion                                       10
Platform contribution                                35

Cook: 280 − ingredients 150 − packaging 12
          − utilities 10 − labor 40 − waste 8          60
```

This is not a supplier quote or profit forecast. Cook labor includes shopping, preparation, packing, cleanup, and administration. The refund allowance is a forecast input, not an extra automatic seller deduction or a cost to double-count alongside actual realized refunds.

### 27.3 Economics of the new experience choices

**Express:** Recalculate courier utilization, preparation slack, spoilage, support, and claims. A faster headline ETA that destroys contribution or safety is not an advantage.

**Pickup:** Recalculate fees and promotion eligibility; account for safe staging, no-shows, premises/access costs, and seller consent. Removing customer delivery charges does not remove every fulfillment cost.

**Plans:** Allocate discount, delivery/service charge, payment cost, refunds, and seller payable to each occurrence. Multi-day prepayment is not immediate profit.

**Larger family baskets:** Test actual willingness to pay, portion expectations, kitchen capacity, and transport costs. Do not assume courier cost remains fixed for arbitrarily large trays.

### 27.4 Funding and break-even

At EGP 35 average order contribution and illustrative EGP 150,000 monthly fixed cost, break-even requires 4,286 orders/month, about 165/day over 26 days. A small neighborhood pilot cannot be presented as already supporting a full central team.

The baseline's illustrative 12-week envelope of EGP 630,000–1,152,000 before working-capital reserve and unpriced exclusions is retained only as a planning reference. Obtain current scoped quotes and update the investment case for any added express, pickup, plan, kitchen, insurance, or compliance cost.

Maintain a weekly cash forecast with provider timing, seller liabilities, courier payments, refunds, taxes, and fixed spend. Do not finance operations from money owed to cooks or future meal-plan fulfillment.

## 28. Technology and implementation contracts

### 28.1 Architecture

Use a maintainable modular monolith, transactional database, durable jobs/outbox, scoped media storage, and provider adapters. A proposed fit is supported ASP.NET Core, SQL Server, optional measured Redis use, Flutter customer/cook clients where justified, and a secured operations web dashboard. Confirm versions/vendor contracts at build kickoff.

Modules: identity/access, seller eligibility, catalog, menu/slot capacity, quotes/pricing, orders, production/batches, delivery/custody, payments/refunds, seller ledger/payout, cases/safety, messaging, configuration, and reporting/audit.

Keep the UI fast through efficient reads and local drafts, while server transactions preserve stock and money. Neither a client cache nor a push notification is the financial source of truth.

### 28.2 Important data contracts

- **Shopping context:** Destination/address version, date/window, mode, preparation type, and language.
- **Catalog version:** Seller/kitchen, recipe, portion/variant, modifiers, ingredient/allergen declaration, category, and approval status.
- **Quote:** Line prices, discount sponsorship, fees, applicable tax treatment, total, expiry, and policy versions.
- **Reservation:** Portions plus kitchen/delivery capacity, expiry, and idempotent commitment/release state.
- **Order snapshot:** Accepted seller, items/options, address/recipient, date/window, price/policies, payment references, and commitments.
- **Production evidence:** Approved location, batch, ingredient lots, checks, package IDs, and deviations.
- **Financial record:** Capture/authorization, refund, chargeback, seller payable, payout, COD collection/remittance, and correcting entries.
- **Plan/occurrence:** Explicit entitlement/date, allocated money, fulfillment, cancellation/reschedule link, and remaining liability.

Do not expose sensitive kitchen coordinates in public catalog payloads and rely on the client to hide them. Do not trust client-provided prices, seller balances, safety approvals, or status transitions.

### 28.3 Non-negotiable invariants

1. Eligible approved supply, sufficient capacity, accepted quote, and verified payment/COD are required to confirm an order.
2. Two requests cannot commit the same last portion or oversubscribe a shared slot resource.
3. One payment event cannot confirm or charge an order twice.
4. Financial retries cannot duplicate refunds/payouts or exceed the remaining refundable/payable balance.
5. Safety quarantine blocks fulfillment regardless of payment status.
6. Delivered/canceled/failed states retain history; corrections are audited.
7. Reassignments revoke obsolete courier access and handoff credentials.
8. Existing commercial snapshots cannot be rebuilt from today's mutable catalog/configuration.
9. Every charged plan occurrence has fulfilled or unresolved/refunded liability state.
10. Customer, cook, courier, support, finance, and safety actions are authorized by object and role.

### 28.4 Client and integration behavior

Use stable reason codes with localized text; distinguish `SLOT_FULL`, `KITCHEN_PAUSED`, `ITEM_CHANGED`, `ADDRESS_UNSERVICEABLE`, `PAYMENT_UNCERTAIN`, and `REFUND_PENDING`. Return enough recovery context without leaking private records.

Adopt useful imported envelope/upload/idempotency conventions only through Bety-specific reviewed contracts. Do not pretend missing Dash API documents define this product. Bety uses Egyptian Arabic rather than the source project's Saudi locale.

Verify provider signatures, currency/amount, replay protection, and callback ordering. Use bounded retries, dead-letter/review queues, and reconciliation jobs. Durable business events notify clients; they do not replace database constraints.

### 28.5 Security and analytics

Apply privileged MFA, least privilege, protected secrets, restricted exports, expiring private media access, safe uploads, appropriate encryption, retention controls, and audit review. Strip location metadata from public images and keep identity evidence private.

Events for conversion/operations should contain pseudonymous IDs and business states, not raw identity, household address, health details, or free-text notes. A future AI feature cannot override eligibility, safety, financial rules, or approved commitments.

## 29. Deployment, rollout, and measurement

### 29.1 Deployment readiness

Separate development, staging, and production credentials/data/providers. Review hosting, subprocessors, backups, and cross-border processing with the privacy/legal workstream. Use synthetic or anonymized staging data.

Build/review pipelines include compilation, focused domain/integration tests, secrets/dependency checks, backward-compatible migrations, staging rehearsal, release sign-off, limited rollout, and monitored containment/rollback. Test database restore and provider reconciliation before launch.

Independent controls can pause checkout, a zone/window, kitchen, batch, payment method, COD, and payout release while preserving order lookup, cases, refunds, and necessary operations.

### 29.2 Twelve-week gated implementation sequence

- **Weeks 1–2:** Interviews, production/legal feasibility, recipe costing, zone/partner decisions, competitor mobile verification backlog, and customer/cook/admin prototypes.
- **Weeks 3–4:** Approved controlled food trials, packaging/route validation, traceability/incident rehearsal, and a capped concierge pilot if required permissions are in place.
- **Weeks 5–6:** Core M1 identity, context/serviceability, catalog, menu/calendar, configuration, carts, quotes, stock/slot reservation, and approved payment.
- **Weeks 7–8:** Cook production, custody/delivery, cases/refunds, seller statements, reconciliation/payout, Arabic/accessibility/security/recovery QA. Target an MVP candidate rather than an unconditional public launch.
- **Weeks 9–10:** Controlled neighborhood beta, daily reconciliation, correction of observed friction/failures, and mature-cohort repeat measurement.
- **Weeks 11–12:** Evidence-based public neighborhood launch or continued controlled correction; decide next funding tranche and which M2/M3 capability earns implementation.

Prepare each week's material decisions in the previous review; prepare Week 1 at kickoff. External approvals may extend the calendar. No schedule permits bypassing legal, food, financial, or readiness gates.

### 29.3 Proposed launch measures

- At least 95% of confirmed orders fulfilled within the agreed window over a meaningful recent sample.
- Cook/platform-caused cancellation below 3% and missing/wrong-item events below 2%, with root causes reviewed.
- No unresolved critical food-safety control failure; absence of reported illness in a small sample is not proof of safety.
- No unexplained financial discrepancy older than two business days without an accountable external-dependency plan.
- Positive variable contribution before acquisition subsidy and a credible path after ordinary promotions.
- Acceptable cook contribution after actual labor, assessed by distribution rather than only top sellers.
- Proposed 30-day repeat target of at least 30% for fully observed first-order households, separated by promotion/full-price cohorts.

These are internal hypotheses, not competitor or industry benchmarks. Use samples, confidence, qualitative evidence, and incident review rather than automatically scaling because one number barely passes.

### 29.4 Experience instrumentation

Measure serviceability failure, address-change basket impact, search-to-item reach, required-choice errors, cart conflict exits, quote changes, checkout drop-off, payment uncertainty age, duplicate attempt prevention, accurate status coverage, response/refund age, reorder completion, and cook production friction.

Test whether better portions, date clarity, and repeat shortcuts improve contribution and trust. Do not experiment with undisclosed fees, reduced safety controls, or weaker statutory remedies.

## 30. Decision log and completion criteria

### 30.1 Decisions proposed in this version

- Familiar merchant/meal shopping sequence with Arabic-first home/orders/account navigation.
- Visible destination and meal date throughout; address changes include impact review.
- One kitchen/window per order with explicit basket conflicts.
- Structured configuration and truthful portion/arrival information.
- A binding all-in quote before payment commitment.
- Scheduled M1, with express/pickup/plans/catering/finish-at-home as separate gated capabilities.
- Finite plans end automatically and identify every fulfillment; no default auto-renewal.
- Bety owns the resolution record, traceability, financial integrity, and fair seller treatment.

### 30.2 Decisions awaiting evidence or professional approval

Exact zone, production route, participating cooks, approved foods, price acceptance, fee/tax configuration, provider fund flow, courier handling limits, cancellation retention, seller-loss guarantee, payout schedule, messaging vendors, budget, and native/web distribution.

Do not mark a proposal approved merely because it appears in this document. Use a named decision owner, evidence, effective version/date, and affected flow/scenario references.

### 30.3 Coverage and release sign-off

The [edge-case catalog](./bety-flow-edge-case-catalog.md) covers F01–F28 with concrete triggers, expected outcomes, accountable owners, and release labels. It is a requirements catalog, not proof that a built app has passed tests.

Every enabled flow needs prototype review, critical scenario validation, real operational rehearsal where relevant, and consistent Arabic/English customer/cook/support wording. Later features remain disabled until their own criteria pass.

No finite document guarantees every possible real-world failure. Add observed incidents and new product decisions to the catalog, preserve rule consistency, and repeat affected checks before rollout.

### 30.4 Document relationship

The [original plan](./bety-business-and-experience-plan.md) retains its original content and business/compliance baseline. This document is the competitor-informed experience proposal. The [research study](./research/competitor-experience-study.md) records evidence and limits. The [edge-case catalog](./bety-flow-edge-case-catalog.md) turns the proposal into concrete release criteria. The [README](./README.md) is the entry point for all four.
