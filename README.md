# Tapin2 API Documentation

I am systematically probing the Tapin2 API to verify responses against live sandbox data. If you have experience with this endpoint or have sample JSON responses (sanitized), please feel free to contribute to this documentation.

![Progress](https://img.shields.io/badge/Documentation_Progress-88%25-blue)

## Endpoint Registry

Explore the documented and planned endpoints below. Categories are grouped by their primary function.

<details markdown="1">
<summary><b>Category Endpoints (67%)</b></summary>

| Method | Endpoint | Status |
| :--- | :--- | :--- |
| GET | [`v2/venues/{venueId}/locations/{locationId}/categories`](endpoints/categories.md) | ✅ Documented |
| POST | [`{version}/Category`](endpoints/category_post.md) | ❌ Blocked (500 Error) |
| GET | [`{version}/Category`](endpoints/category_get.md) | ✅ Documented |

</details>

<details markdown="1">
<summary><b>Event Endpoints (100%)</b></summary>

| Method | Endpoint | Status |
| :--- | :--- | :--- |
| GET | [`v2/venues/{venueId}/events/{minDate}/{maxDate}`](endpoints/events_range.md) | ✅ Documented |
| POST | [`v2/events/{minDate}/{maxDate}`](endpoints/events_search_post.md) | ✅ Documented |
| GET | [`v2/venues/{venueId}/events/current`](endpoints/events_current.md) | ✅ Documented |
| GET | [`v2/venues/{venueId}/events/{eventId}`](endpoints/event_details.md) | ✅ Documented |

</details>

<details markdown="1">
<summary><b>Location Endpoints (100%)</b></summary>

| Method | Endpoint | Status |
| :--- | :--- | :--- |
| GET | [`v2/locations/{venueId}?includePreorder={includePreorder}`](endpoints/locations_preorder.md) | ✅ Documented |
| GET | [`v2/venues/{venueId}/locations`](endpoints/venue_locations.md) | ✅ Documented |

</details>

<details markdown="1">
<summary><b>Order & Cart Endpoints (100%)</b></summary>

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
<summary><b>Product Endpoints (83%)</b></summary>

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
<summary><b>Venue & VenueGroup Endpoints (100%)</b></summary>

| Method | Endpoint | Status |
| :--- | :--- | :--- |
| GET | [`v2/venues/{venueId}/details`](endpoints/venue_details.md) | ✅ Documented |
| GET | [`v2/venues/{venueId}/discounts`](endpoints/venue_discounts.md) | ✅ Documented |
| GET | [`v2/venues/{venueId}/translations`](endpoints/venue_translations.md) | ✅ Documented |
| GET | [`v2/venues/{venueId}/content`](endpoints/venue_content.md) | ✅ Documented |
| GET | [`v2/venuegroups/{groupId}/venueids`](endpoints/venue_groups.md) | ✅ Documented |

</details>

<details markdown="1">
<summary><b>Other Endpoints (Seat, User, Report, etc.) (86%)</b></summary>

| Category | Method | Endpoint | Status |
| :--- | :--- | :--- | :--- |
| **Seat** | GET | [`v2/venues/{venueId}/events/{eventId}/sections`](endpoints/venue_sections.md) | ✅ Documented |
| **User** | GET | [`v4/venues/{venueId}/users/pin/{pin}`](endpoints/user_by_pin.md) | ✅ Documented |
| **Report** | GET | [`v1/venues/{venueId}/reports/{reportType}/{fromDate}/{toDate}`](endpoints/reports_v1.md) | ✅ Documented |
| **Error** | POST | [`v2/venues/{venueId}/error`](endpoints/PLANNED.md) | 📝 Planned |
| **Print** | GET | [`v3/venues/{venueId}/locations/{locationId}/print`](endpoints/location_print_queue.md) | ✅ Documented |
| **Tab** | GET | [`v2/venues/{venueId}/tabs/unprinted`](endpoints/tabs_unprinted.md) | ✅ Documented |
| **Tab2** | GET | [`v4/venues/{venueId}/tabs/{tabId}`](endpoints/tab_details_v4.md) | ✅ Documented |

</details>

## Known Deficiencies & Limitations

The following endpoints are currently documented but known to return errors or empty responses in the sandbox environment:

- **v1/venues/{venueId}/reports**: Returns `500 Internal Server Error`. This legacy reporting system appears to be deprecated in favor of the Management Console's export features.
- **v2/venues/{venueId}/tabs/unprinted**: Returns `404 Not Found`. Unprinted activity is likely handled via the standard order fulfillment endpoints.
- **v2/venuegroups/{groupId}/venueids**: Returns `404 Not Found`. This endpoint may require specific venue group permissions or is inactive in the sandbox.
- **v2/venues/{venueId}/orders/unprinted**: Returns `[]` unless active, unprinted orders exist in the current event context.
- **Suite-based Event Data**: Current event calls for suite-based venues frequently return `null` outside of specific preorder windows.
- **Translations (`v2/venues/{venueId}/translations`)**: Currently returns an empty object `{}` for all tested venues. The mechanism for populating these strings is currently unverified.
- **POST {version}/Category**: Returns `500 Internal Server Error` with `System.NullReferenceException` in `SubmitIntegrationsAsync`. This appears to be a backend failure when synchronizing with POS integrations in the sandbox environment.
- **Cart Management (`v2/cart/*`)**: `add`, `remove`, and `updatequantity` endpoints consistently return `500 Internal Server Error` (`ArgumentNullException`) during the `OrderingCutOff` validation phase, even when provided with valid `eventId` and `locationId` contexts from active orders.
- **Timestamp Discrepancies**: The API exhibits inconsistent timezone behavior. Event-related endpoints (`v2/events/*`) typically return localized venue time (PST), while Order-related endpoints (`v2/venues/{id}/orders/*`) return timestamps in **UTC**.

## Project Context

- [METHODOLOGY.md](METHODOLOGY.md): Detailed explanation of my API verification and documentation process.

- [CHANGELOG.md](CHANGELOG.md): A log of all updates to this documentation.

### Key Venue Types
- **Suites**: Suite-based service including tabs and packages.
- **Concessions**: Standard physical concession stand service.

---
[← Back to Top](#tapin2-api-documentation)