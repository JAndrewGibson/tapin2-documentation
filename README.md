# Tapin2 API Documentation

This repository serves as the primary, complete source of documentation for the Tapin2 API, verified against live sandbox responses.

![Progress](https://progress-bar.dev/47/?title=Documentation%20Complete&width=400)

## Endpoint Registry

Explore the documented and planned endpoints below. Categories are grouped by their primary function.

<details markdown="1">
<summary><b>Category Endpoints</b></summary>

| Method | Endpoint | Status |
| :--- | :--- | :--- |
| GET | [`v2/venues/{venueId}/locations/{locationId}/categories`](endpoints/categories.md) | 📝 Planned |
| POST | [`{version}/Category`](endpoints/category_post.md) | 📝 Planned |
| GET | [`{version}/Category`](endpoints/category_get.md) | 📝 Planned |

</details>

<details markdown="1">
<summary><b>Event Endpoints</b></summary>

| Method | Endpoint | Status |
| :--- | :--- | :--- |
| GET | [`v2/venues/{venueId}/events/{minDate}/{maxDate}`](endpoints/events_range.md) | ✅ Documented |
| POST | [`v2/events/{minDate}/{maxDate}`](endpoints/events_range_post.md) | 📝 Planned |
| GET | [`v2/venues/{venueId}/events/current`](endpoints/events_current.md) | ✅ Documented |
| GET | [`v2/venues/{venueId}/events/{eventId}`](endpoints/event_details.md) | ✅ Documented |

</details>

<details markdown="1">
<summary><b>Location Endpoints</b></summary>

| Method | Endpoint | Status |
| :--- | :--- | :--- |
| GET | [`v2/locations/{venueId}?includePreorder={includePreorder}`](endpoints/locations_preorder.md) | ✅ Documented |
| GET | [`v2/venues/{venueId}/locations`](endpoints/venue_locations.md) | ✅ Documented |

</details>

<details markdown="1">
<summary><b>Order & Cart Endpoints</b></summary>

| Method | Endpoint | Status |
| :--- | :--- | :--- |
| GET | [`v2/venues/{venueId}/orders/unprinted`](endpoints/orders_unprinted.md) | ✅ Documented |
| GET | [`v1/venues/{venueId}/orders/unprinted`](endpoints/orders_unprinted_v1.md) | 📝 Planned |
| POST | [`v2/cart/add`](endpoints/cart_add.md) | 📝 Planned |
| POST | [`v2/cart/remove`](endpoints/cart_remove.md) | 📝 Planned |
| POST | [`v2/cart/updatequantity`](endpoints/cart_update_quantity.md) | 📝 Planned |
| GET | [`v4/venues/{venueId}/events/{eventId}/orders/small`](endpoints/orders_small.md) | 📝 Planned |
| POST | [`v4/venues/{venueId}/orders/{orderId}/items/{itemId}/bump`](endpoints/order_item_bump.md) | 📝 Planned |

</details>

<details markdown="1">
<summary><b>Product Endpoints</b></summary>

| Method | Endpoint | Status |
| :--- | :--- | :--- |
| GET | [`v2/venues/{venueId}/products`](endpoints/products_venue.md) | ✅ Documented |
| GET | [`v2/venues/{venueId}/inventory`](endpoints/venue_inventory.md) | ✅ Documented |
| GET | [`v2/venues/{venueId}/products/{productId}/status`](endpoints/product_status.md) | ✅ Documented |
| GET | [`v2/venues/{venueId}/locations/{locationId}/products`](endpoints/location_products.md) | ✅ Documented |
| GET | [`v4/venues/{venueId}/locations/{locationId}/products/small`](endpoints/products_small.md) | ✅ Documented |
| GET | [`v2/venues/{venueId}/events/{eventId}/products`](endpoints/products_event.md) | 📝 Planned |

</details>

<details markdown="1">
<summary><b>Venue & VenueGroup Endpoints</b></summary>

| Method | Endpoint | Status |
| :--- | :--- | :--- |
| GET | [`v2/venues/{venueId}/details`](endpoints/venue_details.md) | ✅ Documented |
| GET | [`v2/venues/{venueId}/discounts`](endpoints/venue_discounts.md) | ✅ Documented |
| GET | [`v2/venues/{venueId}/translations`](endpoints/venue_translations.md) | ✅ Documented |
| GET | [`v2/venues/{venueId}/content`](endpoints/venue_content.md) | ✅ Documented |
| GET | [`v2/venuegroups/{groupId}/venueids`](endpoints/venue_group_ids.md) | 📝 Planned |

</details>

<details markdown="1">
<summary><b>Other Endpoints (Seat, User, Report, etc.)</b></summary>

| Category | Method | Endpoint | Status |
| :--- | :--- | :--- | :--- |
| **Seat** | GET | [`v2/venues/{venueId}/events/{eventId}/sections`](endpoints/venue_sections.md) | ✅ Documented |
| **User** | GET | [`v4/venues/{venueId}/users/pin/{pin}`](endpoints/user_by_pin.md) | 📝 Planned |
| **Report** | GET | [`v1/venues/{venueId}/reports/{reportType}/{fromDate}/{toDate}`](endpoints/reports_v1.md) | 📝 Planned |
| **Error** | POST | [`v2/venues/{venueId}/error`](endpoints/error_report.md) | 📝 Planned |
| **Print** | GET | [`v3/venues/{venueId}/locations/{locationId}/print`](endpoints/location_print_queue.md) | 📝 Planned |
| **Tab** | GET | [`v2/venues/{venueId}/tabs/unprinted`](endpoints/tabs_unprinted.md) | 📝 Planned |
| **Tab2** | GET | [`v4/venues/{venueId}/tabs/{tabId}`](endpoints/tab_details_v4.md) | 📝 Planned |

</details>

## Known Deficiencies & Limitations

- **Translations (`v2/venues/{venueId}/translations`)**: Currently returns an empty object `{}` for all tested venues. The mechanism for populating these strings is currently unverified.
- **Suite-based Event Data**: Current event calls for suite-based venues frequently return `null` outside of specific preorder windows.
- **Unprinted Orders (`v2/venues/{venueId}/orders/unprinted`)**: Frequently returns an empty array `[]` in sandboxes. Verification of the full order schema requires an active, unprinted order.
- **Reports (v1)**: Currently returning `500 Server Error` on initial probes. Likely requires specific permissions or a more complex query.

## Project Context

- [METHODOLOGY.md](METHODOLOGY.md): Detailed explanation of our API verification and documentation process.

### Key Venue Types
- **Suites**: Suite-based service including tabs and packages.
- **Concessions**: Standard physical concession stand service.

---
[← Back to Top](#tapin2-api-documentation)