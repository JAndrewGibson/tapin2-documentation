# Tapin2 API Documentation

This repository serves as the primary, complete source of documentation for the Tapin2 API, verified against live sandbox responses.

## Endpoint Registry

Explore the documented and planned endpoints below. Categories are grouped by their primary function.

<details>
<summary><b>Category Endpoints</b></summary>

| Method | Endpoint | Status | Documentation |
| :--- | :--- | :--- | :--- |
| GET | `v2/venues/{venueId}/locations/{locationId}/categories` | 📝 Planned | [categories.md](endpoints/categories.md) |
| POST | `{version}/Category` | 📝 Planned | [category_post.md](endpoints/category_post.md) |
| GET | `{version}/Category` | 📝 Planned | [category_get.md](endpoints/category_get.md) |

</details>

<details>
<summary><b>Event Endpoints</b></summary>

| Method | Endpoint | Status | Documentation |
| :--- | :--- | :--- | :--- |
| GET | `v2/venues/{venueId}/events/{minDate}/{maxDate}` | ✅ Documented | [events_range.md](endpoints/events_range.md) |
| POST | `v2/events/{minDate}/{maxDate}` | 📝 Planned | [events_range_post.md](endpoints/events_range_post.md) |
| GET | `v2/venues/{venueId}/events/current` | ✅ Documented | [events_current.md](endpoints/events_current.md) |
| GET | `v2/venues/{venueId}/events/{eventId}` | ✅ Documented | [event_details.md](endpoints/event_details.md) |

</details>

<details>
<summary><b>Location Endpoints</b></summary>

| Method | Endpoint | Status | Documentation |
| :--- | :--- | :--- | :--- |
| GET | `v2/locations/{venueId}?includePreorder={includePreorder}` | ✅ Documented | [locations_preorder.md](endpoints/locations_preorder.md) |
| GET | `v2/venues/{venueId}/locations` | ✅ Documented | [venue_locations.md](endpoints/venue_locations.md) |

</details>

<details>
<summary><b>Order & Cart Endpoints</b></summary>

| Method | Endpoint | Status | Documentation |
| :--- | :--- | :--- | :--- |
| GET | `v2/venues/{venueId}/orders/unprinted` | ✅ Documented | [orders_unprinted.md](endpoints/orders_unprinted.md) |
| GET | `v1/venues/{venueId}/orders/unprinted` | 📝 Planned | [orders_unprinted_v1.md](endpoints/orders_unprinted_v1.md) |
| POST | `v2/cart/add` | 📝 Planned | [cart_add.md](endpoints/cart_add.md) |
| POST | `v2/cart/remove` | 📝 Planned | [cart_remove.md](endpoints/cart_remove.md) |
| POST | `v2/cart/updatequantity` | 📝 Planned | [cart_update_quantity.md](endpoints/cart_update_quantity.md) |
| GET | `v4/venues/{venueId}/events/{eventId}/orders/small` | 📝 Planned | [orders_small.md](endpoints/orders_small.md) |
| POST | `v4/venues/{venueId}/orders/{orderId}/items/{itemId}/bump` | 📝 Planned | [order_item_bump.md](endpoints/order_item_bump.md) |

</details>

<details>
<summary><b>Product Endpoints</b></summary>

| Method | Endpoint | Status | Documentation |
| :--- | :--- | :--- | :--- |
| GET | `v2/venues/{venueId}/products` | ✅ Documented | [products_venue.md](endpoints/products_venue.md) |
| GET | `v2/venues/{venueId}/inventory` | ✅ Documented | [venue_inventory.md](endpoints/venue_inventory.md) |
| GET | `v2/venues/{venueId}/products/{productId}/status` | ✅ Documented | [product_status.md](endpoints/product_status.md) |
| GET | `v2/venues/{venueId}/locations/{locationId}/products` | ✅ Documented | [location_products.md](endpoints/location_products.md) |
| GET | `v4/venues/{venueId}/locations/{locationId}/products/small` | ✅ Documented | [products_small.md](endpoints/products_small.md) |
| GET | `v2/venues/{venueId}/events/{eventId}/products` | 📝 Planned | [products_event.md](endpoints/products_event.md) |

</details>

<details>
<summary><b>Venue & VenueGroup Endpoints</b></summary>

| Method | Endpoint | Status | Documentation |
| :--- | :--- | :--- | :--- |
| GET | `v2/venues/{venueId}/details` | ✅ Documented | [venue_details.md](endpoints/venue_details.md) |
| GET | `v2/venues/{venueId}/discounts` | ✅ Documented | [venue_discounts.md](endpoints/venue_discounts.md) |
| GET | `v2/venues/{venueId}/translations` | ✅ Documented | [venue_translations.md](endpoints/venue_translations.md) |
| GET | `v2/venues/{venueId}/content` | ✅ Documented | [venue_content.md](endpoints/venue_content.md) |
| GET | `v2/venuegroups/{groupId}/venueids` | 📝 Planned | [venue_group_ids.md](endpoints/venue_group_ids.md) |

</details>

<details>
<summary><b>Other Endpoints (Seat, User, Report, etc.)</b></summary>

| Category | Method | Endpoint | Status | Documentation |
| :--- | :--- | :--- | :--- | :--- |
| **Seat** | GET | `v2/venues/{venueId}/events/{eventId}/sections` | ✅ Documented | [venue_sections.md](endpoints/venue_sections.md) |
| **User** | GET | `v4/venues/{venueId}/users/pin/{pin}` | 📝 Planned | [user_by_pin.md](endpoints/user_by_pin.md) |
| **Report** | GET | `v1/venues/{venueId}/reports/{reportType}/{fromDate}/{toDate}` | 📝 Planned | [reports_v1.md](endpoints/reports_v1.md) |
| **Error** | POST | `v2/venues/{venueId}/error` | 📝 Planned | [error_report.md](endpoints/error_report.md) |
| **Print** | GET | `v3/venues/{venueId}/locations/{locationId}/print` | 📝 Planned | [location_print_queue.md](endpoints/location_print_queue.md) |
| **Tab** | GET | `v2/venues/{venueId}/tabs/unprinted` | 📝 Planned | [tabs_unprinted.md](endpoints/tabs_unprinted.md) |
| **Tab2** | GET | `v4/venues/{venueId}/tabs/{tabId}` | 📝 Planned | [tab_details_v4.md](endpoints/tab_details_v4.md) |

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