
# Tapin2 API Documentation

I am systematically probing the Tapin2 API to verify responses against live sandbox data. This project tracks the verification status of all major endpoints and identifies known deficiencies in the sandbox environment.

**Known Issues:** [View Known Issues](extra-documents/known-issues.md)

## Status Legend
- ✅ **Documented**: Verified with live sandbox data. Structure and examples are confirmed.
- ❌ **Blocked**: Endpoint exists but consistently returns 404/500/Empty. See the [Known Issues](extra-documents/known-issues.md) for details.
- 📝 **Planned**: Not yet probed or documented in this cycle.

## Endpoint Registry

Explore the documented endpoints below. Click a category to expand its list of endpoints.

<details markdown="1">
<summary><b>📂 Category Endpoints</b></summary>

| Method | Endpoint | Status |
| :--- | :--- | :--- |
| GET | [`v2/venues/{venueId}/locations/{locationId}/categories`](endpoints/categories.md) | ✅ Documented |
| POST | [`{version}/Category`](endpoints/category_post.md) | ❌ Blocked (500 Error) |
| GET | [`{version}/Category`](endpoints/category_get.md) | ✅ Documented |

</details>

<details markdown="1">
<summary><b>📂 Event Endpoints</b></summary>

| Method | Endpoint | Status |
| :--- | :--- | :--- |
| GET | [`v2/venues/{venueId}/events/{minDate}/{maxDate}`](endpoints/events_range.md) | ✅ Documented |
| POST | [`v2/events/{minDate}/{maxDate}`](endpoints/events_search_post.md) | ✅ Documented |
| GET | [`v2/venues/{venueId}/events/current`](endpoints/events_current.md) | ✅ Documented |
| GET | [`v2/venues/{venueId}/events/{eventId}`](endpoints/event_details.md) | ✅ Documented |

</details>

<details markdown="1">
<summary><b>📂 Location Endpoints</b></summary>

| Method | Endpoint | Status |
| :--- | :--- | :--- |
| GET | [`v2/locations/{venueId}?includePreorder={includePreorder}`](endpoints/locations_preorder.md) | ✅ Documented |
| GET | [`v2/venues/{venueId}/locations`](endpoints/venue_locations.md) | ✅ Documented |

</details>

<details markdown="1">
<summary><b>📂 Order & Cart Endpoints</b></summary>

| Method | Endpoint | Status |
| :--- | :--- | :--- |
| GET | [`v2/venues/{venueId}/orders/unprinted`](endpoints/orders_unprinted.md) | ✅ Documented |
| GET | [`v1/venues/{venueId}/orders/unprinted`](endpoints/orders_unprinted_v1.md) | ✅ Documented |
| POST | [`v2/cart/add`](endpoints/cart_add.md) | ❌ Blocked (500 Error) |
| POST | [`v2/cart/remove`](endpoints/cart_remove.md) | ❌ Blocked (500 Error) |
| POST | [`v2/cart/updatequantity`](endpoints/cart_update_quantity.md) | ❌ Blocked (500 Error) |
| GET | [`v4/venues/{venueId}/events/{eventId}/orders/small`](endpoints/orders_small.md) | ✅ Documented |
| POST | [`v4/venues/{venueId}/orders/{orderId}/items/{itemId}/bump`](endpoints/order_item_bump.md) | ✅ Documented |

</details>

<details markdown="1">
<summary><b>📂 Product Endpoints</b></summary>

| Method | Endpoint | Status |
| :--- | :--- | :--- |
| GET | [`v2/venues/{venueId}/products`](endpoints/products_venue.md) | ✅ Documented |
| GET | [`v2/venues/{venueId}/inventory`](endpoints/venue_inventory.md) | ✅ Documented |
| GET | [`v2/venues/{venueId}/products/{productId}/status`](endpoints/product_status.md) | ✅ Documented |
| GET | [`v2/venues/{venueId}/locations/{locationId}/products`](endpoints/location_products.md) | ✅ Documented |
| GET | [`v4/venues/{venueId}/locations/{locationId}/products/small`](endpoints/products_small.md) | ✅ Documented |
| GET | [`v2/venues/{venueId}/events/{eventId}/products`](endpoints/products_event.md) | ✅ Documented |

</details>

<details markdown="1">
<summary><b>📂 Venue & VenueGroup Endpoints</b></summary>

| Method | Endpoint | Status |
| :--- | :--- | :--- |
| GET | [`v2/venues/{venueId}/details`](endpoints/venue_details.md) | ✅ Documented |
| GET | [`v2/venues/{venueId}/discounts`](endpoints/venue_discounts.md) | ✅ Documented |
| GET | [`v2/venues/{venueId}/translations`](endpoints/venue_translations.md) | ✅ Documented |
| GET | [`v2/venues/{venueId}/content`](endpoints/venue_content.md) | ✅ Documented |
| GET | [`v2/venuegroups/{groupId}/venueids`](endpoints/venue_groups.md) | ✅ Documented |

</details>

<details markdown="1">
<summary><b>📂 Other Endpoints (Seat, User, Report, etc.)</b></summary>

| Category | Method | Endpoint | Status |
| :--- | :--- | :--- | :--- |
| **Seat** | GET | [`v2/venues/{venueId}/events/{eventId}/sections`](endpoints/venue_sections.md) | ✅ Documented |
| **User** | GET | [`v4/venues/{venueId}/users/pin/{pin}`](endpoints/user_by_pin.md) | ✅ Documented |
| **Report** | GET | [`v1/venues/{venueId}/reports/{reportType}/{fromDate}/{toDate}`](endpoints/reports_v1.md) | ✅ Documented |
| **Error** | POST | [`v2/venues/{venueId}/error`](endpoints/venue_error_log.md) | ✅ Documented |
| **Print** | GET | [`v3/venues/{venueId}/locations/{locationId}/print`](endpoints/location_print_queue.md) | ✅ Documented |
| **Tab** | GET | [`v2/venues/{venueId}/tabs/unprinted`](endpoints/tabs_unprinted.md) | ✅ Documented |
| **Tab2** | GET | [`v4/venues/{venueId}/tabs/{tabId}`](endpoints/tab_details_v4.md) | ✅ Documented |

</details>

<br>

## Agentic Usage

This repository includes a specialized guide for AI agents tasked with developing applications that consume the Tapin2 API:

- [🤖 API Usage Guide for Agents](extra-documents/USAGE_AGENTS.md): Critical technical constraints, timezone rules, and model references for API integration.

## Project Context

- [METHODOLOGY](extra-documents/METHODOLOGY.md): Detailed explanation of my API verification and documentation process.
- [KNOWN ISSUES](extra-documents/known-issues.md): In-depth look at non-functional endpoints and behavioral caveats.
- [CHANGELOG](extra-documents/CHANGELOG.md): A log of all updates to this documentation.

### Key Venue Types
- **Suites**: Suite-based service including tabs and packages.
- **Concessions**: Standard physical concession stand service.

---
[← Back to Top](#tapin2-api-documentation)