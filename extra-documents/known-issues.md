# Known Issues & API Caveats

This document catalogs all non-functional endpoints, behavioral inconsistencies, and architectural caveats identified during the systematic probing of the Tapin2 API in the sandbox environment.

> **IMPORTANT:**
> **Source of Truth**: These findings are based on live API responses verified using the methodology described in [METHODOLOGY.md](METHODOLOGY.md). Successfully resolving these issues will likely require direct coordination with **Tapin2 Support** ([support@tapin2.co](mailto:support@tapin2.co)).

## 1. Blocked & Non-Functional Endpoints (500 Error)

These endpoints consistently return a `500 Internal Server Error` despite providing valid request bodies and contexts.

| Endpoint | Method | Identified Issue |
| :--- | :--- | :--- |
| [`{version}/Category`](../endpoints/category_post.md) | POST | Fails with `NullReferenceException` in `SubmitIntegrationsAsync`. This suggests a failure in the synchronization layer between Tapin2 and downstream POS integrations (e.g., Quest, Bypass). |
| [`v2/cart/add`](../endpoints/cart_add.md) | POST | Fails with `ArgumentNullException` (Parameter: `source`) in `OrderingCutOff`. This occurs even when valid `eventId` and `locationId` contexts are provided from active orders. |
| [`v2/cart/remove`](../endpoints/cart_remove.md) | POST | Shares backend controller logic with the `add` endpoint and exhibits identical failure behavior. |
| [`v2/cart/updatequantity`](../endpoints/cart_update_quantity.md) | POST | Shares backend controller logic with the `add` endpoint and exhibits identical failure behavior. |
| [`v1/venues/{venueId}/reports/*`](../endpoints/reports_v1.md) | GET | Returns 500. This legacy reporting system appears to be deprecated in favor of the newer Management Console exports. |
| [`v2/cart/discount/balance`](../endpoints/cart_discount_balance.md) | GET | Returns 500 Internal Server Error in sandbox environment. |
| [`v2/venues/{venueId}/events/{eventId}/seats/{seatId}/categories`](../endpoints/venues_events_seats_categories.md) | GET | Returns 500 Internal Server Error in sandbox environment. |
| [`{version}/Venue`](../endpoints/venue_version.md) | GET | Returns 500 Internal Server Error in sandbox environment. |
| [`v3/venues/{venueId}/local/print?eventId={eventId}&locationId={locationId}&orderId={orderId}&tabId={tabId}&printTemplate={printTemplate}`](../endpoints/venues_local_print_v3.md) | GET | Returns 500 Internal Server Error in sandbox environment. |
| [`v1/venues/{venueId}/reports/{reportType}/{fromDate}/{fromMins}/{toDate}/{toMins}?addDayToEndOfRange={addDayToEndOfRange}`](../endpoints/venues_reports_v1.md) | GET | Returns 500 Internal Server Error in sandbox environment. |
| [`v1/venues/{venueId}/reports/{reportType}/events/{eventId}`](../endpoints/venues_reports_events_v1.md) | GET | Returns 500 Internal Server Error in sandbox environment. |
| [`v2/venues/{venueId}/reports/{reportType}/{fromDate}/{toDate}`](../endpoints/venues_reports.md) | GET | Returns 500 Internal Server Error in sandbox environment. |
| [`v2/venues/{venueId}/reports/{reportType}/{fromDate}/{fromMins}/{toDate}/{toMins}?addDayToEndOfRange={addDayToEndOfRange}`](../endpoints/venues_reports_2.md) | GET | Returns 500 Internal Server Error in sandbox environment. |
| [`v2/venues/{venueId}/reports/{reportType}/events/{eventId}`](../endpoints/venues_reports_events.md) | GET | Returns 500 Internal Server Error in sandbox environment. |
| [`yd/venues/{venueId}/orders/modified/{fromDate}/{toDate}`](../endpoints/venues_orders_modified_yd.md) | GET | Returns 500 Internal Server Error in sandbox environment. |

## 2. Inconsistent Timezone Behavior

A major discrepancy exists between how different controllers handle date and time:

*   **Event-related Endpoints** (`v2/events/*`, `v2/venues/{id}/events/*`): Return timestamps in **Local Venue Time** (e.g., Pacific Standard Time).
*   **Order-related Endpoints** (`v2/venues/{id}/orders/*`, `v2/venues/{id}/orders/unprinted`): Return timestamps in **UTC**.
*   **Recommendation**: Developers must check the `venue.timeZoneInfo` object returned in order responses to properly localize timestamps for end-users.

## 3. Inactive or Unverified Endpoints (404 / Empty)

These endpoints return `404 Not Found` or empty results, suggesting they are either inactive in the sandbox or require feature flags.

| Endpoint | Method | Observed Behavior |
| :--- | :--- | :--- |
| [`v2/venues/{venueId}/tabs/unprinted`](../endpoints/tabs_unprinted.md) | GET | Returns 404. All unprinted activity for both concessions and suites appears to be routed through the standard v2 orders endpoint. |
| [`v2/venuegroups/{groupId}/venueids`](../endpoints/venue_groups.md) | GET | Returns 404. This may require specific Venue Group administrator permissions. |
| [`v2/venues/{venueId}/translations`](../endpoints/venue_translations.md) | GET | Returns an empty object `{}`. The mechanism for populating and retrieving these strings remains unverified. |
| [`v2/venues/{venueId}/sections/{sectionId}/locations`](../endpoints/venues_sections_locations.md) | GET | Returns 404 Not Found (endpoint inactive or no data matches query context). |
| [`v1/venues/{venueId}/orders?count={count}`](../endpoints/venues_orders_v1.md) | GET | Returns 404 Not Found (endpoint inactive or no data matches query context). |
| [`v1/venues/{venueId}/orders/{orderId}`](../endpoints/venues_orders_v1_2.md) | GET | Returns 404 Not Found (endpoint inactive or no data matches query context). |
| [`v2/venues/{venueId}/events/{eventId}/orders/{orderId}/refund?userId={userId}&managerPin={managerPin}`](../endpoints/venues_events_orders_refund.md) | GET | Returns 404 Not Found (endpoint inactive or no data matches query context). |
| [`v4/venues/{venueId}/events/{eventId}/device/{deviceSerial}/orders/small`](../endpoints/venues_events_device_orders_small_v4.md) | GET | Returns 404 Not Found (endpoint inactive or no data matches query context). |
| [`v4/venues/{venueId}/orders/small/phone/{phone}`](../endpoints/venues_orders_small_phone_v4.md) | GET | Returns 404 Not Found (endpoint inactive or no data matches query context). |
| [`v2/venues/{venueId}/events/{eventId}/seats/{seatId}/categories/{categoryId}/products?dob={dob}`](../endpoints/venues_events_seats_categories_products.md) | GET | Returns 404 Not Found (endpoint inactive or no data matches query context). |
| [`v2/venues/{venueId}/user/{pin}/products`](../endpoints/venues_user_products.md) | GET | Returns 404 Not Found (endpoint inactive or no data matches query context). |
| [`v2/global/enums/{enumType}/{asKeyValuePairs}/{nameFirst}`](../endpoints/global_enums.md) | GET | Returns 404 Not Found (endpoint inactive or no data matches query context). |
| [`v3/venues/{venueId}/vendors/{locationId}/print`](../endpoints/venues_vendors_print_v3.md) | GET | Returns 404 Not Found (endpoint inactive or no data matches query context). |
| [`v2/venues/{venueId}/events/{eventId}/sections/{sectionId}/rows`](../endpoints/venues_events_sections_rows.md) | GET | Returns 404 Not Found (endpoint inactive or no data matches query context). |
| [`v2/venues/{venueId}/events/{eventId}/sections/{sectionId}/rows/{row}/numbers`](../endpoints/venues_events_sections_rows_numbers.md) | GET | Returns 404 Not Found (endpoint inactive or no data matches query context). |
| [`v2/venues/{venueId}/events/{eventId}/seats/{sectionId}/{row}/{seatNumber}`](../endpoints/venues_events_seats.md) | GET | Returns 404 Not Found (endpoint inactive or no data matches query context). |

## 4. Sandbox Behavioral Caveats

*   **Suite-based Event Windows**: The `v2/venues/{id}/events/current` endpoint for suite-based venues frequently returns `null` if called outside of a specific pre-order window or if no event is actively "current" in the system.
*   **Unprinted Orders Logic**: The `v2/venues/{id}/orders/unprinted` endpoint returns an empty array `[]` unless there are active, unpaid, or unfulfilled orders in the system. Verification requires placing a test order via a terminal or mobile app first.
*   **Modifier Flatness in v4**: While standard v2 orders return highly nested modifier objects, the `v4/.../orders/small` endpoint returns a "flattened" modifier list within each item, including only `id`, `title`, and `priceDiff`.

## 5. Security & Data Integrity

*   **Sanitization Rule**: To comply with security requirements, all documentation and examples use generic placeholders (e.g., `VENUE_ID_A`, `1001`) instead of real production IDs.
*   **State-Modifying Operations**: All `PUT` and `POST` (creation/update) operations should be tested with specific user permission and safe test items provided by the venue administrator to avoid data corruption.

## 6. Next Steps for Developers

If your integration requires any of the blocked or non-functional endpoints listed above, please contact the **Tapin2 Integration Team** at [support@tapin2.co](mailto:support@tapin2.co) to:
1.  Verify if the endpoint is active for your specific Venue ID.
2.  Ensure that all necessary POS integrations (e.g., Quest, Bypass) are properly mapped in your sandbox instance.
3.  Request a specific `DeviceId` or `SessionToken` if required for Cart operations.

## 7. Additional Sandbox Blocked & Administrative Endpoints

These endpoints returned alternative failure codes during sandbox verification, indicating administrative restrictions or method exclusions.

| Endpoint | Method | Observed Behavior |
| :--- | :--- | :--- |
| [`{version}/Location`](../endpoints/location_version.md) | GET | Returns 401 Unauthorized (requires advanced or administrative API scope). |
| [`{version}/Order2`](../endpoints/order2_version.md) | GET | Returns 401 Unauthorized (requires advanced or administrative API scope). |
| [`{version}/Order4`](../endpoints/order4_version.md) | GET | Returns 401 Unauthorized (requires advanced or administrative API scope). |
| [`{version}/OrderItem`](../endpoints/orderitem_version.md) | GET | Returns 401 Unauthorized (requires advanced or administrative API scope). |
| [`{version}/Product`](../endpoints/product_version.md) | GET | Returns 401 Unauthorized (requires advanced or administrative API scope). |
| [`{version}/Product4`](../endpoints/product4_version.md) | GET | Returns 401 Unauthorized (requires advanced or administrative API scope). |
| [`{version}/Report`](../endpoints/report_version.md) | GET | Returns 401 Unauthorized (requires advanced or administrative API scope). |
| [`{version}/ReportV2`](../endpoints/reportv2_version.md) | GET | Returns 401 Unauthorized (requires advanced or administrative API scope). |
| [`{version}/Tab`](../endpoints/tab_version.md) | GET | Returns 401 Unauthorized (requires advanced or administrative API scope). |
| [`{version}/Tab2`](../endpoints/tab2_version.md) | GET | Returns 401 Unauthorized (requires advanced or administrative API scope). |
| [`{version}/User`](../endpoints/user_version.md) | GET | Returns 401 Unauthorized (requires advanced or administrative API scope). |
| [`{version}/Event`](../endpoints/event_version.md) | GET | Returns 405 Method Not Allowed (GET method disabled for version). |
| [`v2/venues/{venueId}/orders/modified/{fromDate}/{toDate}`](../endpoints/venues_orders_modified.md) | GET | Consistently times out in sandbox (Read Timeout > 15s). |
| [`v2/venues/{venueId}/orders/modified/{fromDate}/{fromMins}/{toDate}/{toMins}?addDayToEndOfRange={addDayToEndOfRange}`](../endpoints/venues_orders_modified_2.md) | GET | Returns 400 Bad Request (parameters invalid or malformed). |
| [`v4/venues/{venueId}/orders/small/modified/{fromDate}/{toDate}`](../endpoints/venues_orders_small_modified_v4.md) | GET | Consistently times out in sandbox (Read Timeout > 15s). |
| [`v4/venues/{venueId}/orders/small/modified/{fromDate}/{fromMins}/{toDate}/{toMins}?addDayToEndOfRange={addDayToEndOfRange}`](../endpoints/venues_orders_small_modified_v4_2.md) | GET | Returns 400 Bad Request (parameters invalid or malformed). |
| [`{version}/Seat`](../endpoints/seat_version.md) | GET | Returns 405 Method Not Allowed (GET method disabled for version). |

---
[← Back to Main Registry](../README.md)
