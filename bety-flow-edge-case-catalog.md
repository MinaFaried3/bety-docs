# Bety flow and edge-case catalog

**Version:** 2.0 proposal · **Prepared:** 27 October 2026

[New experience blueprint](./bety-competitor-informed-plan.md) · [Competitor evidence](./research/competitor-experience-study.md) · [Original plan, unchanged](./bety-business-and-experience-plan.md)

This catalog specifies 140 scenarios across F01–F28. Expected outcomes are Bety requirements, not observed competitor behavior or evidence of completed software testing. Happy-path sequences and screen definitions live in the blueprint. No finite catalog exhausts every possible incident; add observed failures and retest affected rules.

**P0:** Release-blocking financial, authorization, safety, or commitment integrity for the applicable feature. **P1:** Required experience/recovery behavior before enabling the feature. M1/M2/M3 identify the earliest planned release; a later mode remains off until its own controls pass.

Each scenario identifies trigger, expected user/system outcome, accountable owner, and release. Validation must include the relevant customer, cook, courier, support, ledger, capacity, and audit effects; a screenshot alone cannot establish financial or safety correctness.

## Flow index

- [F01 — Arrival, identity, and return to intent](#f01--arrival-identity-and-return-to-intent)
- [F02 — Address and serviceability](#f02--address-and-serviceability)
- [F03 — Date, window, and shopping intent](#f03--date-window-and-shopping-intent)
- [F04 — Home and navigation](#f04--home-and-navigation)
- [F05 — Search](#f05--search)
- [F06 — Categories, filters, and sort](#f06--categories-filters-and-sort)
- [F07 — Kitchen profile and menu](#f07--kitchen-profile-and-menu)
- [F08 — Meal configuration](#f08--meal-configuration)
- [F09 — Cart and kitchen conflict](#f09--cart-and-kitchen-conflict)
- [F10 — Prices and promotions](#f10--prices-and-promotions)
- [F11 — Checkout and reservation](#f11--checkout-and-reservation)
- [F12 — Payments and confirmation](#f12--payments-and-confirmation)
- [F13 — Orders and tracking](#f13--orders-and-tracking)
- [F14 — Changes and cancellation](#f14--changes-and-cancellation)
- [F15 — Cases, refunds, and safety reports](#f15--cases-refunds-and-safety-reports)
- [F16 — Reviews, favorites, and reorder](#f16--reviews-favorites-and-reorder)
- [F17 — Account and privacy](#f17--account-and-privacy)
- [F18 — Notifications and communication](#f18--notifications-and-communication)
- [F19 — Finite plans and occurrence accounting](#f19--finite-plans-and-occurrence-accounting)
- [F20 — Approved pickup](#f20--approved-pickup)
- [F21 — Requests, catering, and preparation types](#f21--requests-catering-and-preparation-types)
- [F22 — Cook onboarding and eligibility](#f22--cook-onboarding-and-eligibility)
- [F23 — Menu, cost, and capacity controls](#f23--menu-cost-and-capacity-controls)
- [F24 — Production and packing](#f24--production-and-packing)
- [F25 — Courier custody and handoff](#f25--courier-custody-and-handoff)
- [F26 — Reconciliation and payout](#f26--reconciliation-and-payout)
- [F27 — Admin, traceability, and safety response](#f27--admin-traceability-and-safety-response)
- [F28 — Accessibility, outages, and recovery](#f28--accessibility-outages-and-recovery)

## F01 — Arrival, identity, and return to intent

**Blueprint:** [F01 specification](./bety-competitor-informed-plan.md#4-f01--arrival-identity-and-returning-to-intent) · **Default owner:** Identity/product · **Earliest release:** M1

### EC001 — Sign-in interrupts a meal choice

**When:** A guest configures a dish and is asked to verify identity.

**Expected:** Preserve choices, context, and return target. After verification return to the dish or checkout, refresh price/stock, and require a new commitment if anything material changed.

**Owner:** Identity/product · **Priority:** P1 · **Release:** M1

### EC002 — Expired or repeated verification codes

**When:** The customer uses an expired code or requests many codes.

**Expected:** Show an actionable expiry/rate-limit state with safe retry and recovery. Do not expose whether another account exists or indefinitely lock an active order out of support.

**Owner:** Identity/product · **Priority:** P0 · **Release:** M1

### EC003 — Private order deep link

**When:** A link to an order is opened under the wrong account.

**Expected:** Require the authorized account and deny private content. Link previews, error text, analytics, and redirects must not reveal order, recipient, or household details.

**Owner:** Identity/product · **Priority:** P0 · **Release:** M1

### EC004 — Guest and account carts collide

**When:** A returning account already has a basket when guest verification completes.

**Expected:** Show both contexts and ask which draft to keep or restore. Never combine kitchens, silently double quantities, or treat either draft as reserved inventory.

**Owner:** Identity/product · **Priority:** P1 · **Release:** M1

### EC005 — Deleted meal or expired campaign link

**When:** A shared link references removed content or an ended offer.

**Expected:** Explain unavailability and offer current eligible discovery. Do not crash, resurrect an expired price, or redirect to an unrelated meal as though it were the original.

**Owner:** Identity/product · **Priority:** P1 · **Release:** M1


## F02 — Address and serviceability

**Blueprint:** [F02 specification](./bety-competitor-informed-plan.md#5-f02--address-serviceability-and-location-changes) · **Default owner:** Location/operations · **Earliest release:** M1

### EC006 — Location permission denied

**When:** The customer declines GPS or approximate location is inaccurate.

**Expected:** Provide manual search/pin/address entry with equal access. The phone position remains a suggestion and cannot overwrite a confirmed delivery destination.

**Owner:** Location/operations · **Priority:** P1 · **Release:** M1

### EC007 — Outdated address search response

**When:** The customer types a new destination while a previous request is still running.

**Expected:** Version or cancel responses; only the latest intended destination updates results. Confirm the pin and locality before replacing the shopping context.

**Owner:** Location/operations · **Priority:** P1 · **Release:** M1

### EC008 — Address change invalidates basket

**When:** A new address changes eligible kitchens, slots, or fees.

**Expected:** Preview affected lines and the new quote. Let the customer retain the old destination or review the changed basket; do not silently delete or charge it.

**Owner:** Location/operations · **Priority:** P0 · **Release:** M1

### EC009 — Address book edited during delivery

**When:** The customer edits a saved address after an order is confirmed.

**Expected:** Update future defaults only. The active order retains its accepted address snapshot and any actual delivery change follows the reviewed amendment process.

**Owner:** Location/operations · **Priority:** P0 · **Release:** M1

### EC010 — Pin outside supported boundary

**When:** A plausible text address has a pin beyond the delivery polygon or inaccessible route.

**Expected:** Block commitment, explain serviceability, and offer pin correction or a valid destination. No payment can create an unfulfillable order.

**Owner:** Location/operations · **Priority:** P0 · **Release:** M1


## F03 — Date, window, and shopping intent

**Blueprint:** [F03 specification](./bety-competitor-informed-plan.md#6-f03--meal-date-delivery-window-and-shopping-intent) · **Default owner:** Scheduling/operations · **Earliest release:** M1

### EC011 — Midnight changes relative labels

**When:** A basket opened before midnight is resumed the next day.

**Expected:** Render absolute accepted dates and recalculate availability. Do not reinterpret a stored date as the new tomorrow or move an existing order.

**Owner:** Scheduling/operations · **Priority:** P0 · **Release:** M1

### EC012 — Cutoff closes while reviewing

**When:** A customer reaches payment after the slot cutoff with an old quote.

**Expected:** Enforce server time, shorten/expire reservations correctly, and offer a valid slot. Do not trust the client countdown or accept a new late commitment.

**Owner:** Scheduling/operations · **Priority:** P0 · **Release:** M1

### EC013 — Slot fills during browsing

**When:** Other confirmed orders consume the remaining delivery/production capacity.

**Expected:** Refresh eligibility and offer the next actual slot with basket effects. No charge occurs for the full slot.

**Owner:** Scheduling/operations · **Priority:** P0 · **Release:** M1

### EC014 — Date change changes supply

**When:** A favorite kitchen has different dishes on the newly selected day.

**Expected:** Retain intent as a draft, identify unavailable lines, and ask for valid replacements. Revalidate prices, options, cutoffs, and promotion eligibility.

**Owner:** Scheduling/operations · **Priority:** P1 · **Release:** M1

### EC015 — Express collection has stale eligibility

**When:** An item looked express-eligible before its batch or courier capacity changed.

**Expected:** Recheck batch life, preparation, route, and courier capacity. Remove the express promise or offer a valid scheduled alternative before commitment.

**Owner:** Scheduling/operations · **Priority:** P0 · **Release:** M2


## F04 — Home and navigation

**Blueprint:** [F04 specification](./bety-competitor-informed-plan.md#7-f04--home-navigation-and-merchandising) · **Default owner:** Customer experience · **Earliest release:** M1

### EC016 — New user has no order history

**When:** The customer has no favorites, reviews, or previous orders.

**Expected:** Show real serviceable discovery and onboarding guidance. Omit empty personalized modules and do not fabricate popular meals, ratings, or past behavior.

**Owner:** Customer experience · **Priority:** P1 · **Release:** M1

### EC017 — Promotional banner targets another context

**When:** An offer exists but is invalid for the selected date, address, or variant.

**Expected:** Show eligibility accurately and route to the valid context with consent. Do not present an ineligible headline price as the payable price.

**Owner:** Customer experience · **Priority:** P1 · **Release:** M1

### EC018 — Several active orders exist

**When:** The customer has multiple upcoming or checking-payment records.

**Expected:** Provide clear order selection and individual status. A new basket remains independent; no alert or status card overwrites another order.

**Owner:** Customer experience · **Priority:** P1 · **Release:** M1

### EC019 — Bottom overlays hide content

**When:** A sticky cart, tab bar, keyboard, or system inset overlaps a product or action.

**Expected:** Reserve safe layout space and maintain accessible scrolling/focus. Portion, price, required errors, and primary actions remain reachable.

**Owner:** Customer experience · **Priority:** P1 · **Release:** M1

### EC020 — Cached home after supply pause

**When:** A kitchen is paused while an older home remains cached.

**Expected:** Refresh visible eligibility and revalidate every add/checkout. Cached marketing content cannot bypass a seller or safety stop-sale.

**Owner:** Customer experience · **Priority:** P0 · **Release:** M1


## F05 — Search

**Blueprint:** [F05 specification](./bety-competitor-informed-plan.md#8-f05--search-and-relevant-discovery) · **Default owner:** Search/product · **Earliest release:** M1

### EC021 — Arabic and transliterated names

**When:** A buyer searches common spelling variants or mixed Arabic/English dish names.

**Expected:** Retrieve reviewed relevant matches while preserving original display names. Do not turn ingredient search into an allergen-free or medical suitability guarantee.

**Owner:** Search/product · **Priority:** P1 · **Release:** M1

### EC022 — Responses arrive out of order

**When:** An older broad query returns after a newer specific query.

**Expected:** Display results for the current query/context only. Add actions use stable IDs, not positions in a stale list.

**Owner:** Search/product · **Priority:** P1 · **Release:** M1

### EC023 — Empty results have different causes

**When:** A phrase has no match, a slot has no supply, or the network failed.

**Expected:** Show the specific state and relevant recovery: edit query, clear filter, change date, or retry. Do not report network failure as absence of kitchens.

**Owner:** Search/product · **Priority:** P1 · **Release:** M1

### EC024 — Kitchen-scoped search mistaken for global

**When:** The buyer searches inside one kitchen and expects all sellers.

**Expected:** Label the current scope and provide an explicit global-search action that preserves query and delivery context.

**Owner:** Search/product · **Priority:** P1 · **Release:** M1

### EC025 — Result becomes unavailable before adding

**When:** A result meal is unpublished, sold out, or held after the search response.

**Expected:** Revalidate on action, explain the changed state, and show eligible alternatives. Never add an obsolete recipe version silently.

**Owner:** Search/product · **Priority:** P0 · **Release:** M1


## F06 — Categories, filters, and sort

**Blueprint:** [F06 specification](./bety-competitor-informed-plan.md#9-f06--categories-filters-sorting-and-collections) · **Default owner:** Discovery/product · **Earliest release:** M1

### EC026 — Different portion sizes sorted as price

**When:** Results include individual plates, small variants, and family trays.

**Expected:** Label comparable units and from-prices. Sorting cannot imply a smaller portion is better value than a differently measured meal without a valid comparison.

**Owner:** Discovery/product · **Priority:** P1 · **Release:** M1

### EC027 — Ingredient filter misread as allergy safety

**When:** A customer filters vegetarian ingredients or excludes an ingredient term.

**Expected:** State the filter scope and provide reviewed allergen/cross-contact information. Unsupported allergy guarantees cannot be inferred from search metadata.

**Owner:** Discovery/product · **Priority:** P0 · **Release:** M1

### EC028 — Filter combination yields zero results

**When:** Several otherwise valid filters eliminate all current supply.

**Expected:** Show active filters and an easy reset or targeted relaxation. Keep date/address stable and distinguish no supply from a technical failure.

**Owner:** Discovery/product · **Priority:** P1 · **Release:** M1

### EC029 — Counts remain stale after context change

**When:** A category count was computed for another address or date.

**Expected:** Refresh counts and visible results together. Do not claim currently deliverable kitchens from an unfiltered global total.

**Owner:** Discovery/product · **Priority:** P1 · **Release:** M1

### EC030 — Nearest kitchen cannot deliver soonest

**When:** A nearby kitchen is busy while another has an earlier valid slot.

**Expected:** Treat proximity and arrival as different sort signals. Honor preparation, route, and delivery capacity instead of equating distance with speed.

**Owner:** Discovery/product · **Priority:** P1 · **Release:** M1


## F07 — Kitchen profile and menu

**Blueprint:** [F07 specification](./bety-competitor-informed-plan.md#10-f07--kitchen-and-cook-profile) · **Default owner:** Catalog/supply · **Earliest release:** M1

### EC031 — Closed now but future slots exist

**When:** A cook is not operating immediately but accepts tomorrow preorders.

**Expected:** Show the next valid date and reviewed menu. Avoid both a misleading open promise and a blanket closed screen that hides valid future ordering.

**Owner:** Catalog/supply · **Priority:** P1 · **Release:** M1

### EC032 — Kitchen safety or eligibility hold

**When:** A hold is applied after customers open the kitchen page.

**Expected:** Block new commitments and affected dispatches; list existing orders for review. No deep link, cached page, or quick-add path bypasses the hold.

**Owner:** Catalog/supply · **Priority:** P0 · **Release:** M1

### EC033 — New cook has no ratings

**When:** An assessed kitchen has no eligible customer reviews.

**Expected:** Show a truthful new/unrated state and assessment explanation. Do not manufacture a five-star rating or imply official certification.

**Owner:** Catalog/supply · **Priority:** P1 · **Release:** M1

### EC034 — Profile leaks a private production address

**When:** Public profile data includes household coordinates or identifying metadata.

**Expected:** Return only approved public location/disclosures. Exact private pickup details remain server-restricted to authorized operational roles.

**Owner:** Catalog/supply · **Priority:** P0 · **Release:** M1

### EC035 — Menu navigation loses place

**When:** The user taps a section, opens a meal, then closes it.

**Expected:** Keep section/scroll behavior consistent and restore position. The compact header and active chip remain accessible without covering items.

**Owner:** Catalog/supply · **Priority:** P1 · **Release:** M1


## F08 — Meal configuration

**Blueprint:** [F08 specification](./bety-competitor-informed-plan.md#11-f08--meal-details-variants-and-add-to-cart) · **Default owner:** Catalog/checkout · **Earliest release:** M1

### EC036 — Required choices unresolved

**When:** The customer taps quick add on a meal with size/protein/sauce requirements.

**Expected:** Open configuration, identify required groups, enforce minimum/maximum choices, and block an invalid add. Never guess a safety-relevant ingredient choice.

**Owner:** Catalog/checkout · **Priority:** P0 · **Release:** M1

### EC037 — Variant promotion differs by size

**When:** Only one weight has a discount and quantity changes.

**Expected:** Show that selected variant price and full line total. Recalculate stock and discounts; do not spread the offer to every size.

**Owner:** Catalog/checkout · **Priority:** P0 · **Release:** M1

### EC038 — Distinct configurations merged

**When:** Two units of one dish have different sauces or proteins.

**Expected:** Keep separate lines and production instructions. Only identical recipe/variant/modifier/slot configurations may merge.

**Owner:** Catalog/checkout · **Priority:** P0 · **Release:** M1

### EC039 — Ingredient changes during configuration

**When:** A cook changes a recipe after the customer opens its sheet.

**Expected:** Revalidate version and disclosures before commitment. Require acceptance of a material change or keep the accepted safe version where valid.

**Owner:** Catalog/checkout · **Priority:** P0 · **Release:** M1

### EC040 — Allergen request in free text

**When:** A note asks for guaranteed absence of an allergen or unsupported ingredient substitution.

**Expected:** Do not treat the note as an accepted safety change. Provide approved information, route to qualified review, or decline the unsupported request.

**Owner:** Catalog/checkout · **Priority:** P0 · **Release:** M1


## F09 — Cart and kitchen conflict

**Blueprint:** [F09 specification](./bety-competitor-informed-plan.md#12-f09--cart-saved-baskets-and-kitchen-conflicts) · **Default owner:** Cart/checkout · **Earliest release:** M1

### EC041 — Second kitchen added

**When:** A buyer with an active kitchen basket adds another seller item.

**Expected:** Offer keep current or explicit save/replace. Do not silently create a second delivery, combined order, or extra fee.

**Owner:** Cart/checkout · **Priority:** P1 · **Release:** M1

### EC042 — Draft resumed after cutoff

**When:** A persisted basket is opened after its stock/window/quote expired.

**Expected:** Explain affected lines, refresh availability/prices, and offer a valid date. The saved draft is not treated as reserved inventory.

**Owner:** Cart/checkout · **Priority:** P0 · **Release:** M1

### EC043 — Last line removed

**When:** The customer decrements the final unit or clears the basket.

**Expected:** Use confirmation or a safe undo pattern and an honest empty state. Do not leave a stale sticky total or accidental checkout capability.

**Owner:** Cart/checkout · **Priority:** P1 · **Release:** M1

### EC044 — Add-more loses kitchen/date

**When:** The customer returns from cart to browse more meals.

**Expected:** Restore the originating kitchen, section, scroll position, and selected window. Another context requires an explicit choice.

**Owner:** Cart/checkout · **Priority:** P1 · **Release:** M1

### EC045 — Same cart edited on two devices

**When:** Concurrent updates change quantities or options.

**Expected:** Detect cart version conflict, return current state, and explain refresh. A stale client cannot overwrite a newer accepted configuration or double an order.

**Owner:** Cart/checkout · **Priority:** P0 · **Release:** M1


## F10 — Prices and promotions

**Blueprint:** [F10 specification](./bety-competitor-informed-plan.md#13-f10--prices-offers-and-complete-totals) · **Default owner:** Pricing/finance · **Earliest release:** M1

### EC046 — Delivery price is still unknown

**When:** Address or window has not been selected.

**Expected:** Label the displayed sum as food subtotal and request missing context. Block payment commitment until an exact complete quote is reviewed.

**Owner:** Pricing/finance · **Priority:** P0 · **Release:** M1

### EC047 — Coupon threshold lost after edit

**When:** Removing a line takes the basket below a promotion or minimum.

**Expected:** Recalculate and explain the discount/fee change before commitment. Preserve accurate sponsor allocation and seller proceeds.

**Owner:** Pricing/finance · **Priority:** P0 · **Release:** M1

### EC048 — Offer expires during checkout

**When:** An accepted-looking coupon or quote expires before the order reserves/commits.

**Expected:** Apply the defined server expiry, issue a fresh quote, and request acceptance of a material difference. No silent higher charge.

**Owner:** Pricing/finance · **Priority:** P0 · **Release:** M1

### EC049 — Partial refund of discounted item

**When:** A sponsored item is missing from a paid order.

**Expected:** Refund the allocated amount actually paid and associated applicable amounts. Reverse sponsor/commission/seller entries consistently without over-refund or double recovery.

**Owner:** Pricing/finance · **Priority:** P0 · **Release:** M1

### EC050 — Several households share one address

**When:** Fraud checks see several legitimate accounts at a compound/building.

**Expected:** Apply contextual abuse review and an appeal. Do not automatically deny valid customer rights or safety remedies solely because an address is shared.

**Owner:** Pricing/finance · **Priority:** P1 · **Release:** M1


## F11 — Checkout and reservation

**Blueprint:** [F11 specification](./bety-competitor-informed-plan.md#14-f11--checkout-and-schedule-commitment) · **Default owner:** Orders/capacity · **Earliest release:** M1

### EC051 — Two customers buy the last portion

**When:** Both checkout requests pass client-side availability.

**Expected:** Database-level commitment allows only the available quantity. The losing request gets a useful refresh/alternative and no impossible charge.

**Owner:** Orders/capacity · **Priority:** P0 · **Release:** M1

### EC052 — Shared kitchen or delivery cap exhausted

**When:** Dish stock exists but oven/labor or courier-window capacity is full.

**Expected:** Evaluate every capacity constraint atomically or with a safe durable reservation. Item stock alone cannot authorize the order.

**Owner:** Orders/capacity · **Priority:** P0 · **Release:** M1

### EC053 — Reservation expires while bank screen is open

**When:** The displayed reservation timer ends before payment returns.

**Expected:** Release once, keep payment outcome separate, and reconcile late provider results. Never presume reservation expiry means funds did not move.

**Owner:** Orders/capacity · **Priority:** P0 · **Release:** M1

### EC054 — Missing recipient or access details

**When:** The customer provides a pin but no deliverable building/contact details.

**Expected:** Validate required information clearly before commitment and preserve the draft. Do not create an order that operations cannot reach.

**Owner:** Orders/capacity · **Priority:** P1 · **Release:** M1

### EC055 — Context changed on checkout return

**When:** The app resumes after address, date, method, or eligibility changed.

**Expected:** Retrieve authoritative context/order state and revalidate quote/capacity. Do not submit a backgrounded stale checkout automatically.

**Owner:** Orders/capacity · **Priority:** P0 · **Release:** M1


## F12 — Payments and confirmation

**Blueprint:** [F12 specification](./bety-competitor-informed-plan.md#15-f12--payment-confirmation-and-uncertainty) · **Default owner:** Payments/engineering · **Earliest release:** M1

### EC056 — Provider timeout with uncertain charge

**When:** The app cannot tell whether the provider accepted a payment.

**Expected:** Keep the existing attempt pending/checking, display a reference, and reconcile authoritatively. Do not invite another charge while the first outcome is unknown.

**Owner:** Payments/engineering · **Priority:** P0 · **Release:** M1

### EC057 — Double tap and duplicate webhook

**When:** The same customer action/provider success is delivered repeatedly.

**Expected:** Use idempotency and unique provider references to create at most one commitment and correct ledger impact. Return the existing outcome.

**Owner:** Payments/engineering · **Priority:** P0 · **Release:** M1

### EC058 — Late success cannot fulfill

**When:** Payment succeeds after expiry and stock, cutoff, or kitchen eligibility now fails.

**Expected:** Do not overbook or move the date. Void/refund through the approved provider flow and expose the unresolved financial state until confirmed.

**Owner:** Payments/engineering · **Priority:** P0 · **Release:** M1

### EC059 — Invalid amount, currency, or callback

**When:** A spoofed/replayed event or mismatched amount arrives.

**Expected:** Reject unauthorized transitions, preserve investigation evidence, and reconcile safely. The client return page is never trusted as payment proof.

**Owner:** Payments/engineering · **Priority:** P0 · **Release:** M1

### EC060 — App dies after payment

**When:** The customer closes or loses the app before confirmation renders.

**Expected:** Recover the same server-side order/attempt after sign-in. Correctly distinguish confirmed, checking, failed, or void/refund pending without asking for blind repayment.

**Owner:** Payments/engineering · **Priority:** P0 · **Release:** M1


## F13 — Orders and tracking

**Blueprint:** [F13 specification](./bety-competitor-informed-plan.md#16-f13--active-orders-and-truthful-tracking) · **Default owner:** Fulfillment/support · **Earliest release:** M1

### EC061 — Events arrive out of order

**When:** A delayed preparing event arrives after courier collection or delivery.

**Expected:** Apply valid transition/version rules, preserve chronology, and do not regress the visible authoritative state. Financial status remains separately modeled.

**Owner:** Fulfillment/support · **Priority:** P0 · **Release:** M1

### EC062 — Marked delivered but not received

**When:** A courier marks handoff complete while the customer disputes receipt.

**Expected:** Open an urgent case, inspect custody/proof, and provide a real next action. Do not treat map proximity as proof or automatically close the dispute.

**Owner:** Fulfillment/support · **Priority:** P0 · **Release:** M1

### EC063 — Scheduled delivery arrives too early

**When:** A courier reaches the customer substantially before the agreed window.

**Expected:** Treat it as a service exception and seek a safe agreed resolution. The customer is not presumed available outside the accepted window.

**Owner:** Fulfillment/support · **Priority:** P1 · **Release:** M1

### EC064 — Live location unavailable

**When:** The partner GPS stream stops or is not integrated.

**Expected:** Show recorded stage and last update honestly, provide support, and avoid a fabricated moving courier or unsupported ETA precision.

**Owner:** Fulfillment/support · **Priority:** P1 · **Release:** M1

### EC065 — Failed payment hidden from history

**When:** No meal was accepted but a hold/refund remains unresolved.

**Expected:** Keep the financial attempt discoverable with its outcome and case access. Do not make the customer lose the evidence because only successful meals are listed.

**Owner:** Fulfillment/support · **Priority:** P0 · **Release:** M1


## F14 — Changes and cancellation

**Blueprint:** [F14 specification](./bety-competitor-informed-plan.md#17-f14--changes-and-cancellation) · **Default owner:** Orders/support/finance · **Earliest release:** M1

### EC066 — Cancellation races with production start

**When:** The cook starts preparation while the customer confirms a cancellation preview.

**Expected:** Use authoritative server state and a transactional boundary. Refresh changed terms before commitment; avoid contradictory stock, production, and refund outcomes.

**Owner:** Orders/support/finance · **Priority:** P0 · **Release:** M1

### EC067 — Confirmed address change request

**When:** The customer asks to send a paid order elsewhere.

**Expected:** Review serviceability, time, custody, fees, and consent. Do not use an address-book edit to redirect an active courier or assume the new destination is feasible.

**Owner:** Orders/support/finance · **Priority:** P0 · **Release:** M1

### EC068 — Supplier asks customer to cancel

**When:** A cook cannot fulfill and requests a voluntary customer cancellation.

**Expected:** Record supplier failure and offer the applicable remedy. Do not impose change-of-mind retention or hide the actual cancellation cause.

**Owner:** Orders/support/finance · **Priority:** P0 · **Release:** M1

### EC069 — Material edit needs more money

**When:** A paid order change increases portions or adds a priced modifier.

**Expected:** In M1 use reviewed cancel/reorder or explicit support resolution. A later amendment requires a valid new commitment/payment adjustment and preserves the old outcome on failure.

**Owner:** Orders/support/finance · **Priority:** P0 · **Release:** M1

### EC070 — Cancellation with no recoverable loss

**When:** After cutoff, food is not committed or the cost is recovered elsewhere.

**Expected:** Base any retention on lawful disclosed evidenced loss. Do not apply maximum penalties automatically or recover the same loss more than once.

**Owner:** Orders/support/finance · **Priority:** P0 · **Release:** M1


## F15 — Cases, refunds, and safety reports

**Blueprint:** [F15 specification](./bety-competitor-informed-plan.md#18-f15--support-refunds-and-safety-reports) · **Default owner:** Support/safety/finance · **Earliest release:** M1

### EC071 — Serious report without a photo

**When:** A customer reports illness, contamination, or an undeclared allergen without images.

**Expected:** Triage immediately, advise stopping consumption, notify safety ownership, and contain affected supply as appropriate. Evidence collection cannot delay required customer protection or reporting.

**Owner:** Support/safety/finance · **Priority:** P0 · **Release:** M1

### EC072 — Repeat refund claimant reports safety issue

**When:** An account under abuse review makes a credible serious complaint.

**Expected:** Handle urgent food safety independently from fraud investigation. Human review may assess abuse, but cannot automatically suppress the safety case.

**Owner:** Support/safety/finance · **Priority:** P0 · **Release:** M1

### EC073 — Two agents refund concurrently

**When:** Separate agents approve overlapping full/partial refunds.

**Expected:** Lock/check remaining refundable balance and use provider idempotency. Prevent over-refund and preserve each decision/audit record.

**Owner:** Support/safety/finance · **Priority:** P0 · **Release:** M1

### EC074 — Refund submitted but fails

**When:** A provider accepts a request then returns failure or no terminal result.

**Expected:** Keep processing/failed status, assign an owner, reconcile, and update the customer. Do not close the case as refunded before authoritative completion.

**Owner:** Support/safety/finance · **Priority:** P0 · **Release:** M1

### EC075 — External help channel unavailable

**When:** A WhatsApp link, chat connection, or support notification fails.

**Expected:** Keep the in-app case record and an approved fallback with hours/expectations. No response is not agreement and an undelivered message is not presented as read.

**Owner:** Support/safety/finance · **Priority:** P1 · **Release:** M1


## F16 — Reviews, favorites, and reorder

**Blueprint:** [F16 specification](./bety-competitor-informed-plan.md#19-f16--reviews-favorites-and-reorder) · **Default owner:** Retention/trust · **Earliest release:** M1

### EC076 — Reorder recipe changed

**When:** An old order contains a dish with new ingredients/options or price.

**Expected:** Build a fresh review, highlight material differences, and validate current disclosures, stock, date, and total. An old receipt cannot authorize a new allergen profile.

**Owner:** Retention/trust · **Priority:** P0 · **Release:** M1

### EC077 — Reorder conflicts with active kitchen

**When:** The old order belongs to a different seller than the current basket.

**Expected:** Apply the explicit kitchen conflict flow. Do not combine sellers or duplicate existing quantities without a visible choice.

**Owner:** Retention/trust · **Priority:** P1 · **Release:** M1

### EC078 — Delivery problem damages cook rating

**When:** A customer wants to rate a late courier after an otherwise correct meal.

**Expected:** Collect appropriate separate feedback and route the actual cause to operations. Avoid attributing delivery failure automatically to meal quality.

**Owner:** Retention/trust · **Priority:** P1 · **Release:** M1

### EC079 — Review exposes private information

**When:** A public review contains a phone, exact household location, harassment, or unrelated family detail.

**Expected:** Moderate the private/abusive content through a documented process, preserve fair criticism, and allow review/appeal. Safety reports also create private cases.

**Owner:** Retention/trust · **Priority:** P0 · **Release:** M1

### EC080 — Favorite kitchen unavailable today

**When:** A saved cook is closed, paused, or not serviceable at the new address.

**Expected:** Keep a truthful saved identity with the correct unavailable/next-slot action. A favorite never bypasses eligibility or becomes an automatic order.

**Owner:** Retention/trust · **Priority:** P1 · **Release:** M1


## F17 — Account and privacy

**Blueprint:** [F17 specification](./bety-competitor-informed-plan.md#20-f17f18--account-privacy-notifications-and-messaging) · **Default owner:** Identity/privacy · **Earliest release:** M1

### EC081 — Phone change takeover attempt

**When:** An attacker requests a new number or recovery using a message alone.

**Expected:** Apply secure verification/recovery, protect active obligations, revoke compromised access, and avoid disclosing another account through lookup responses.

**Owner:** Identity/privacy · **Priority:** P0 · **Release:** M1

### EC082 — Deletion with an outstanding refund

**When:** A customer requests deletion while money or a complaint is unresolved.

**Expected:** Explain necessary retention and provide a secure follow-up route while honoring applicable deletion/marketing rules. Do not erase ledger evidence or block the request indefinitely without basis.

**Owner:** Identity/privacy · **Priority:** P0 · **Release:** M1

### EC083 — Revoked device retains access

**When:** A cook/courier/admin loses authorization or a customer logs out a device.

**Expected:** Enforce server session/object access revocation. Cached private data and deep links cannot continue exposing sensitive records.

**Owner:** Identity/privacy · **Priority:** P0 · **Release:** M1

### EC084 — Object ID changed in a request

**When:** A user tries another customer order, cook payout, or courier assignment ID.

**Expected:** Deny unauthorized object access without revealing private details. Visible role selection is not sufficient authorization.

**Owner:** Identity/privacy · **Priority:** P0 · **Release:** M1

### EC085 — Payment token removal during active order

**When:** A customer removes a saved provider token after paying.

**Expected:** Remove future-use authorization appropriately without erasing the existing transaction/refund reference or breaking necessary reconciliation.

**Owner:** Identity/privacy · **Priority:** P1 · **Release:** M1


## F18 — Notifications and communication

**Blueprint:** [F18 specification](./bety-competitor-informed-plan.md#20-f17f18--account-privacy-notifications-and-messaging) · **Default owner:** Messaging/support · **Earliest release:** M1

### EC086 — Push permission denied

**When:** The customer or cook refuses system notifications.

**Expected:** Keep current orders, required actions, cases, and payment status accessible in-app. Use only approved necessary fallback channels; no false claim that a push was delivered.

**Owner:** Messaging/support · **Priority:** P1 · **Release:** M1

### EC087 — Duplicate or stale notification

**When:** Retries send an old ready/cancel/payment event repeatedly.

**Expected:** Deduplicate and resolve the linked current state. Never regress status or cause a duplicate financial/courier action from a notification tap.

**Owner:** Messaging/support · **Priority:** P0 · **Release:** M1

### EC088 — Chat promise changes a contract

**When:** A cook offers another ingredient, date, fee, or payment destination in chat.

**Expected:** Require an authorized reviewed quote/change workflow and informed customer acceptance. Chat alone cannot amend a paid order or give unsupported safety assurances.

**Owner:** Messaging/support · **Priority:** P0 · **Release:** M1

### EC089 — Message fails or remains unanswered

**When:** A pre-order question is unsent, unread, or beyond response hours.

**Expected:** Display truthful channel state and response expectations; offer support or leave the request unaccepted. Do not treat silence as seller acceptance.

**Owner:** Messaging/support · **Priority:** P1 · **Release:** M1

### EC090 — Harassment or sensitive preview

**When:** A message exposes household/health data or abusive contact.

**Expected:** Provide reporting/contact restrictions and minimize lock-screen content. Preserve necessary evidence under restricted access without cutting off legitimate order support.

**Owner:** Messaging/support · **Priority:** P0 · **Release:** M1


## F19 — Finite plans and occurrence accounting

**Blueprint:** [F19 specification](./bety-competitor-informed-plan.md#21-f19--finite-meal-plans-and-recurring-commitments) · **Default owner:** Plans/finance/operations · **Earliest release:** M3

### EC091 — One future date has no capacity

**When:** A seven-delivery purchase has six available dates and one unavailable date.

**Expected:** Validate all occurrences before charging using a safe all-or-nothing workflow. Offer explicit revised dates instead of creating an unbacked paid entitlement.

**Owner:** Plans/finance/operations · **Priority:** P0 · **Release:** M3

### EC092 — Discount and fees across seven dates

**When:** A hypothetical plan uses seven EGP 350 meals, 5% Bety discount, EGP 35 delivery and EGP 10 service per date.

**Expected:** Show food 2,450 minus 122.50 plus 245 delivery plus 70 service = 2,642.50 before tax adjustment, with sponsor and per-occurrence allocation recorded.

**Owner:** Plans/finance/operations · **Priority:** P0 · **Release:** M3

### EC093 — One occurrence canceled eligibly

**When:** One of the example plan deliveries is fully cancelable before commitment.

**Expected:** Refund its allocated EGP 332.50 food plus 35 delivery plus 10 service = 377.50 before tax adjustment. Update entitlement/liability without retroactive surprise repricing of completed meals.

**Owner:** Plans/finance/operations · **Priority:** P0 · **Release:** M3

### EC094 — Cook unavailable for remaining plan

**When:** Illness, leave, eligibility lapse, or missing menu prevents future committed dates.

**Expected:** List affected occurrences, offer informed eligible alternatives or refunds, and preserve unresolved liability. Do not automatically substitute another cook or unsafe recipe.

**Owner:** Plans/finance/operations · **Priority:** P0 · **Release:** M3

### EC095 — Plan ends or reschedule fails

**When:** The final entitlement is used, or a requested replacement date is unavailable.

**Expected:** End a finite plan without auto-charge. Keep the original occurrence valid until an approved reschedule commits, then link replacement and financial allocation.

**Owner:** Plans/finance/operations · **Priority:** P0 · **Release:** M3


## F20 — Approved pickup

**Blueprint:** [F20 specification](./bety-competitor-informed-plan.md#22-f20f21--pickup-requests-catering-and-finish-at-home) · **Default owner:** Pickup/supply/safety · **Earliest release:** M2

### EC096 — Pickup requested at a private home

**When:** A household kitchen has no approved public collection arrangement.

**Expected:** Hide/block pickup and offer platform delivery or an eligible commercial location. Do not expose the home address to satisfy a cart toggle.

**Owner:** Pickup/supply/safety · **Priority:** P0 · **Release:** M2

### EC097 — Mode switch changes fees or offer

**When:** A delivery basket switches to eligible pickup before commitment.

**Expected:** Revalidate pickup window, address/instructions, charges, and promotion. Present the exact revised quote before acceptance.

**Owner:** Pickup/supply/safety · **Priority:** P0 · **Release:** M2

### EC098 — Pickup code reused or wrong person

**When:** A code is submitted twice or an unauthorized person claims the food.

**Expected:** Verify the authorized collection, consume the handoff once, and record custody. Do not release another order or falsely complete multiple pickups.

**Owner:** Pickup/supply/safety · **Priority:** P0 · **Release:** M2

### EC099 — Customer arrives after safe holding limit

**When:** A paid pickup customer is late or never arrives.

**Expected:** Follow approved holding/no-show policy, contact support, and document food disposition and remedy. Payment does not extend safe holding indefinitely.

**Owner:** Pickup/supply/safety · **Priority:** P0 · **Release:** M2

### EC100 — Kitchen not ready at collection

**When:** A customer arrives in the agreed window but food is not ready.

**Expected:** Show truthful status, provide an operational recovery/remedy, and protect safety. Do not require collection confirmation before actual handoff.

**Owner:** Pickup/supply/safety · **Priority:** P1 · **Release:** M2


## F21 — Requests, catering, and preparation types

**Blueprint:** [F21 specification](./bety-competitor-informed-plan.md#22-f20f21--pickup-requests-catering-and-finish-at-home) · **Default owner:** Custom orders/safety · **Earliest release:** M3

### EC101 — Request mistaken for paid confirmation

**When:** A customer submits dishes, people, budget, and date without an accepted quote.

**Expected:** Label it as a request with response expectations. No order commitment/payment occurs until seller, menu, portions, ingredients, timing, and complete price are accepted.

**Owner:** Custom orders/safety · **Priority:** P0 · **Release:** M3

### EC102 — Expired custom quote accepted

**When:** The customer returns after quote expiry or capacity loss.

**Expected:** Revalidate and issue a current offer. No old screenshot or chat price automatically reserves production or authorizes payment.

**Owner:** Custom orders/safety · **Priority:** P0 · **Release:** M3

### EC103 — Catering exceeds safe throughput

**When:** A normal meal quantity is multiplied for a large event.

**Expected:** Require a reviewed event process, capacity, transport/holding, service scope, and payment/cancellation terms. Do not treat large quantity alone as ordinary checkout eligibility.

**Owner:** Custom orders/safety · **Priority:** P0 · **Release:** M3

### EC104 — Raw or finish-at-home item confused with ready meal

**When:** A customer browses preparation types with different cooking/storage obligations.

**Expected:** Label the actual state clearly, enforce separately approved processes, and block incompatible mixed-mode checkout. Do not imply ready-to-eat safety.

**Owner:** Custom orders/safety · **Priority:** P0 · **Release:** M3

### EC105 — Unsupported dietary or ingredient promise

**When:** A custom request asks for therapeutic suitability or guaranteed allergen-free food.

**Expected:** Use qualified approved factual review or decline. Neither sales pressure nor a seller chat promise bypasses category restrictions or cross-contact limitations.

**Owner:** Custom orders/safety · **Priority:** P0 · **Release:** M3


## F22 — Cook onboarding and eligibility

**Blueprint:** [F22 specification](./bety-competitor-informed-plan.md#23-f22f23--cook-onboarding-menus-and-availability) · **Default owner:** Supply/compliance/safety · **Earliest release:** M1

### EC106 — Identity passes but kitchen fails

**When:** A seller has a verified identity but no valid production route or critical kitchen remediation remains.

**Expected:** Keep sales disabled and communicate precise next steps. Identity approval cannot publish supply or be displayed as food certification.

**Owner:** Supply/compliance/safety · **Priority:** P0 · **Release:** M1

### EC107 — Approval expires before meal date

**When:** A required permission is valid today but not on a future production date.

**Expected:** Block affected future commitments, notify the seller, and list existing affected orders for resolution. Do not rely solely on application-time validity.

**Owner:** Supply/compliance/safety · **Priority:** P0 · **Release:** M1

### EC108 — Production moves to another location

**When:** A cook changes kitchen or uses an unreviewed family location.

**Expected:** Require location-specific eligibility and safety review before new production. Preserve historic location records and review committed orders.

**Owner:** Supply/compliance/safety · **Priority:** P0 · **Release:** M1

### EC109 — Assisted application contains an error

**When:** A staff member enters documents/capacity on behalf of a cook.

**Expected:** Let the cook confirm relevant facts and terms, track the actor, and correct evidence securely. Assistance cannot fabricate consent or hide rejection reasons.

**Owner:** Supply/compliance/safety · **Priority:** P1 · **Release:** M1

### EC110 — Payout verification incomplete

**When:** The cook passes food review but bank/provider onboarding remains unresolved.

**Expected:** Explain the remaining commercial activation requirement and stop unsupported sales/payout promises. Do not collect future seller liabilities through an unapproved flow.

**Owner:** Supply/compliance/safety · **Priority:** P0 · **Release:** M1


## F23 — Menu, cost, and capacity controls

**Blueprint:** [F23 specification](./bety-competitor-informed-plan.md#23-f22f23--cook-onboarding-menus-and-availability) · **Default owner:** Catalog/supply/finance · **Earliest release:** M1

### EC111 — Several dishes share one oven limit

**When:** Each dish individually has stock but their combined batch exceeds practical resources.

**Expected:** Enforce a conservative shared kitchen/resource cap. Independent dish counts cannot multiply the approved production capacity.

**Owner:** Catalog/supply/finance · **Priority:** P0 · **Release:** M1

### EC112 — Cook reduces capacity below orders

**When:** A seller lowers a future limit below already confirmed quantities.

**Expected:** Stop further sale, show existing commitments, and raise an operations decision. Never silently cancel or erase paid obligations.

**Owner:** Catalog/supply/finance · **Priority:** P0 · **Release:** M1

### EC113 — New price or recipe affects old order

**When:** A published meal changes after customers already paid.

**Expected:** Version future sales and retain accepted snapshots. Safety-related changes trigger affected-order review instead of blindly honoring an unsafe old recipe.

**Owner:** Catalog/supply/finance · **Priority:** P0 · **Release:** M1

### EC114 — Promotion makes cook contribution negative

**When:** An offer funds itself from seller proceeds or labor is omitted from costing.

**Expected:** Show sponsor, commission basis, full allocated cost/labor, and expected contribution. Require seller agreement; do not silently discount earnings.

**Owner:** Catalog/supply/finance · **Priority:** P0 · **Release:** M1

### EC115 — Pause has existing commitments

**When:** The cook pauses sales for illness, leave, or workload.

**Expected:** Stop new commitments and prominently list affected existing orders with support actions. A pause is not invisible cancellation or a requirement to cook while ill.

**Owner:** Catalog/supply/finance · **Priority:** P0 · **Release:** M1


## F24 — Production and packing

**Blueprint:** [F24 specification](./bety-competitor-informed-plan.md#24-f24f25--production-packing-couriers-and-handoff) · **Default owner:** Safety/production · **Earliest release:** M1

### EC116 — Critical batch check fails

**When:** A required measurement, ingredient trace, or other critical control is outside its approved limit.

**Expected:** Block readiness/dispatch, isolate affected stock, and route to the qualified safety owner. A courier arrival or paid order cannot override the control.

**Owner:** Safety/production · **Priority:** P0 · **Release:** M1

### EC117 — Power, water, or equipment failure

**When:** Production/holding conditions become uncertain.

**Expected:** Pause affected production/sales, record actual times/readings, assess disposition professionally, and resolve orders. Do not rely on smell, taste, or unvalidated reheating.

**Owner:** Safety/production · **Priority:** P0 · **Release:** M1

### EC118 — Cook reports illness

**When:** The responsible food handler cannot safely work.

**Expected:** Stop affected production, engage operations/backup under an approved route, and remedy customer commitments. Do not pressure the cook to continue or conceal the event.

**Owner:** Safety/production · **Priority:** P0 · **Release:** M1

### EC119 — Packing labels mismatch orders

**When:** Correct portions are assigned to wrong package IDs or modifiers.

**Expected:** Detect at packing/handoff using order/batch/package verification, correct safely, and prevent wrong ingredient/allergen delivery. Preserve an audit trail for any correction.

**Owner:** Safety/production · **Priority:** P0 · **Release:** M1

### EC120 — Ready action captured offline

**When:** The app has not synchronized a cook readiness/check event.

**Expected:** Show pending sync and provide the approved support fallback. Do not dispatch from a client-only checkbox or invent a server acceptance timestamp.

**Owner:** Safety/production · **Priority:** P0 · **Release:** M1


## F25 — Courier custody and handoff

**Blueprint:** [F25 specification](./bety-competitor-informed-plan.md#24-f24f25--production-packing-couriers-and-handoff) · **Default owner:** Delivery/operations · **Earliest release:** M1

### EC121 — Wrong or replaced courier collects

**When:** An obsolete assignment token or unassigned courier attempts pickup.

**Expected:** Validate current assignment and revoke old access/codes. The cook verifies custody transfer before releasing private pickup information/packages.

**Owner:** Delivery/operations · **Priority:** P0 · **Release:** M1

### EC122 — Seal damaged or route limits exceeded

**When:** A courier finds leakage/tampering or cannot meet validated transport conditions.

**Expected:** Escalate and prevent unsafe handoff as appropriate, record disposition, and arrange customer remedy. Do not open/repack casually or resell uncertain-custody food.

**Owner:** Delivery/operations · **Priority:** P0 · **Release:** M1

### EC123 — Completion code requested too early

**When:** A courier asks for the customer delivery PIN at pickup or before arrival.

**Expected:** Reject premature completion, explain the code is for actual handoff, and retain a support fallback with audited proof.

**Owner:** Delivery/operations · **Priority:** P0 · **Release:** M1

### EC124 — Customer unreachable at destination

**When:** Contact attempts fail during the approved waiting period.

**Expected:** Keep required conditions, shorten waiting for safety limits, and let support determine a safe resolution. Do not leave with a neighbor/lobby without an approved agreement.

**Owner:** Delivery/operations · **Priority:** P0 · **Release:** M1

### EC125 — COD cash differs from collectible

**When:** The courier requests extra money or remits less than the authorized amount.

**Expected:** Customer sees exact collectible; record collection/remittance separately and raise a discrepancy. Only explicit contractual deductions explain differences, not an assumed delivery fee.

**Owner:** Delivery/operations · **Priority:** P0 · **Release:** M1


## F26 — Reconciliation and payout

**Blueprint:** [F26 specification](./bety-competitor-informed-plan.md#25-f26f27--settlement-administration-and-safety-control) · **Default owner:** Finance/security · **Earliest release:** M1

### EC126 — Customer collections mistaken for revenue

**When:** Balances include seller payables, refunds, or future plan obligations.

**Expected:** Keep liabilities and platform revenue separate. Cash timing cannot authorize using cook/customer obligations as operating profit.

**Owner:** Finance/security · **Priority:** P0 · **Release:** M1

### EC127 — Same payable enters two payout runs

**When:** Retries or concurrent preparation selects an already scheduled seller balance.

**Expected:** Use unique ledger references and atomic eligibility/release checks. Prevent duplicate payout and reconcile authoritative bank/provider outcomes.

**Owner:** Finance/security · **Priority:** P0 · **Release:** M1

### EC128 — Bank-detail change before payout

**When:** A new payout destination is submitted through account change or messaging.

**Expected:** Reverify through a trusted path, notify the established contact, and apply approved review/cooling controls. A message alone cannot redirect funds.

**Owner:** Finance/security · **Priority:** P0 · **Release:** M1

### EC129 — Refund and chargeback overlap

**When:** A disputed order also has a provider refund or seller adjustment.

**Expected:** Reconcile all linked entries and prevent duplicate recovery. Explain responsibility separately from immediate customer resolution and preserve correcting reversals.

**Owner:** Finance/security · **Priority:** P0 · **Release:** M1

### EC130 — One disputed order holds all earnings

**When:** A small complaint is used to freeze an entire seller balance.

**Expected:** Use justified amount-specific holds with reason, review date, owner, and appeal. Unrelated eligible earnings follow the published payout cycle.

**Owner:** Finance/security · **Priority:** P0 · **Release:** M1


## F27 — Admin, traceability, and safety response

**Blueprint:** [F27 specification](./bety-competitor-informed-plan.md#25-f26f27--settlement-administration-and-safety-control) · **Default owner:** Admin/safety/governance · **Earliest release:** M1

### EC131 — Affected batch includes refunded customers

**When:** A recall lookup filters only currently paid or completed orders.

**Expected:** Retrieve every affected recipient/order regardless of cancellation/refund state where exposure occurred. Refund history cannot erase safety contact responsibility.

**Owner:** Admin/safety/governance · **Priority:** P0 · **Release:** M1

### EC132 — Support attempts privileged action

**When:** An agent tries changing eligibility, payout bank details, or unauthorized refund amount.

**Expected:** Enforce action and object permissions server-side, log attempts, and route to the correct role. UI hiding alone is inadequate.

**Owner:** Admin/safety/governance · **Priority:** P0 · **Release:** M1

### EC133 — Configuration changes after acceptance

**When:** A fee, cutoff, zone, or cancellation policy is edited.

**Expected:** Version future commitments and preserve accepted commercial snapshots. Apply necessary safety containment separately rather than silently repricing old orders.

**Owner:** Admin/safety/governance · **Priority:** P0 · **Release:** M1

### EC134 — Serious hold reopened without evidence

**When:** A kitchen is proposed for reactivation after contamination/critical failure.

**Expected:** Require documented corrective action, qualified safety review, and the approved second authorization. A commercial deadline cannot dismiss containment.

**Owner:** Admin/safety/governance · **Priority:** P0 · **Release:** M1

### EC135 — Bulk admin action selects wrong scope

**When:** A kitchen/batch/zone action would affect more records than intended.

**Expected:** Preview scope and commitments, require appropriate confirmation/permission, audit the action, and provide safe containment/correction without losing history.

**Owner:** Admin/safety/governance · **Priority:** P0 · **Release:** M1


## F28 — Accessibility, outages, and recovery

**Blueprint:** [F28 specification](./bety-competitor-informed-plan.md#26-f28--accessibility-interruption-and-recovery) · **Default owner:** Platform/accessibility · **Earliest release:** M1

### EC136 — Large text or screen reader

**When:** RTL, mixed-script address, a modal, and sticky controls are used with assistive settings.

**Expected:** Maintain reading/focus order and readable units/prices/errors; keep required options and primary actions reachable. State cannot depend only on color or an icon.

**Owner:** Platform/accessibility · **Priority:** P1 · **Release:** M1

### EC137 — Offline cache looks purchasable

**When:** Catalog content remains visible during an outage.

**Expected:** Label stale content and preserve drafts, but require online authoritative quote/capacity/payment commitment. Never accept blind money from cached availability.

**Owner:** Platform/accessibility · **Priority:** P0 · **Release:** M1

### EC138 — Clock, timezone, or daylight-saving boundary

**When:** Device clock is wrong or a Cairo business date crosses a timezone transition.

**Expected:** Compute eligibility and cutoff server-side from timezone-aware rules, store UTC instants, and display an unambiguous local accepted date/window.

**Owner:** Platform/accessibility · **Priority:** P0 · **Release:** M1

### EC139 — Restore replays jobs and provider events

**When:** Database/service recovery brings old jobs and payment callbacks back.

**Expected:** Reconcile authoritative provider/bank state and deduplicate transitions. Restoration must not duplicate an order, refund, seller payout, or customer notification action.

**Owner:** Platform/accessibility · **Priority:** P0 · **Release:** M1

### EC140 — Sensitive information enters telemetry

**When:** An error/export/log contains IDs, exact household location, OTP, payment secrets, or health notes.

**Expected:** Redact/minimize data, restrict access/export, and investigate exposure. Analytics requires only necessary business identifiers and states under the approved privacy policy.

**Owner:** Platform/accessibility · **Priority:** P0 · **Release:** M1

## Release validation protocol

1. Assign named product, operations, safety, finance, and engineering owners for the enabled flow.
2. Record prototype/rehearsal/integration evidence, preconditions, actual result, date, environment, and relevant references for each applicable case.
3. Confirm negative outcomes do not create hidden charges, oversold capacity, unsafe dispatch, privacy exposure, or orphaned liabilities.
4. Resolve P0 failures before enabling the feature; verify P1 usability/recovery with representative devices and Arabic/English layouts.
5. Repeat only affected checks after a relevant change or failure, and add new observed incidents to the catalog.

The structured [scenario matrix](./research/flow-edge-case-matrix.json) carries the same 140 requirements and starts with validation status `not-yet-executed`. It is a specification for future validation, not a claim that tests have passed.
