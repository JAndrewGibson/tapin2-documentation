# API Endpoint Registry

This page tracks the status of documentation for each known Tapin2 API endpoint. Each endpoint should have its own dedicated `.md` file in this directory.

## Core Endpoints

| Category | Method | Endpoint | Status | Documentation File |
| :--- | :--- | :--- | :--- | :--- |
| **Category** | GET | `v2/venues/{venueId}/locations/{locationId}/categories` | 📝 Planned | [categories.md](categories.md) |
| **Category** | POST | `{version}/Category` | 📝 Planned | [category_post.md](category_post.md) |
| **Category** | GET | `{version}/Category` | 📝 Planned | [category_get.md](category_get.md) |
| **Error** | POST | `v2/venues/{venueId}/error` | 📝 Planned | [error_report.md](error_report.md) |
| **Event** | GET | `v2/venues/{venueId}/events/{minDate}/{maxDate}` | ✅ Documented | [events_range.md](events_range.md) |
| **Event** | POST | `v2/events/{minDate}/{maxDate}` | 📝 Planned | [events_range_post.md](events_range_post.md) |
| **Event** | GET | `v2/venues/{venueId}/events/current` | ✅ Documented | [events_current.md](events_current.md) |
| **Event** | GET | `v2/venues/{venueId}/events/{eventId}` | 📝 Planned | [event_details.md](event_details.md) |
| **Location** | GET | `v2/locations/{venueId}?includePreorder={includePreorder}` | ✅ Documented | [locations_preorder.md](locations_preorder.md) |
| **Location** | GET | `v2/venues/{venueId}/locations` | ✅ Documented | [venue_locations.md](venue_locations.md) |
| **Order** | GET | `v1/venues/{venueId}/orders/unprinted` | 📝 Planned | [orders_unprinted_v1.md](orders_unprinted_v1.md) |
| **Order** | GET | `v2/venues/{venueId}/orders/unprinted` | 📝 Planned | [orders_unprinted_v2.md](orders_unprinted_v2.md) |
| **Order** | POST | `v2/cart/add` | 📝 Planned | [cart_add.md](cart_add.md) |
| **Order** | POST | `v2/cart/remove` | 📝 Planned | [cart_remove.md](cart_remove.md) |
| **Order** | POST | `v2/cart/updatequantity` | 📝 Planned | [cart_update_quantity.md](cart_update_quantity.md) |
| **Order4** | GET | `v4/venues/{venueId}/events/{eventId}/orders/small` | 📝 Planned | [orders_small.md](orders_small.md) |
| **OrderItem** | POST | `v4/venues/{venueId}/orders/{orderId}/items/{itemId}/bump` | 📝 Planned | [order_item_bump.md](order_item_bump.md) |
| **Print** | GET | `v3/venues/{venueId}/locations/{locationId}/print` | 📝 Planned | [location_print_queue.md](location_print_queue.md) |
| **Product** | GET | `v2/venues/{venueId}/products` | ✅ Documented | [products_venue.md](products_venue.md) |
| **Product** | GET | `v2/venues/{venueId}/inventory` | ✅ Documented | [venue_inventory.md](venue_inventory.md) |
| **Product** | GET | `v2/venues/{venueId}/products/{productId}/status` | ✅ Documented | [product_status.md](product_status.md) |
| **Product** | GET | `v2/venues/{venueId}/events/{eventId}/products` | 📝 Planned | [products_event.md](products_event.md) |
| **Product4** | GET | `v4/venues/{venueId}/locations/{locationId}/products/small` | 📝 Planned | [products_small.md](products_small.md) |
| **Report** | GET | `v1/venues/{venueId}/reports/{reportType}/{fromDate}/{toDate}` | 📝 Planned | [reports_v1.md](reports_v1.md) |
| **Seat** | GET | `v2/venues/{venueId}/events/{eventId}/sections` | 📝 Planned | [venue_sections.md](venue_sections.md) |
| **Tab** | GET | `v2/venues/{venueId}/tabs/unprinted` | 📝 Planned | [tabs_unprinted.md](tabs_unprinted.md) |
| **Tab2** | GET | `v4/venues/{venueId}/tabs/{tabId}` | 📝 Planned | [tab_details_v4.md](tab_details_v4.md) |
| **User** | GET | `v4/venues/{venueId}/users/pin/{pin}` | 📝 Planned | [user_by_pin.md](user_by_pin.md) |
| **Venue** | GET | `v2/venues/{venueId}/details` | ✅ Documented | [venue_details.md](venue_details.md) |
| **Venue** | GET | `v2/venues/{venueId}/discounts` | ✅ Documented | [venue_discounts.md](venue_discounts.md) |
| **Venue** | GET | `v2/venues/{venueId}/translations` | ✅ Documented | [venue_translations.md](venue_translations.md) |
| **Venue** | GET | `v2/venues/{venueId}/content` | ✅ Documented | [venue_content.md](venue_content.md) |
| **VenueGroup** | GET | `v2/venuegroups/{groupId}/venueids` | 📝 Planned | [venue_group_ids.md](venue_group_ids.md) |

*(Note: This is an initial list. There are many more v1/v2/v4 variations to be added.)*

## Legend
- ✅ Documented
- 🧪 Exploratory (Active testing)
- 📝 Planned
