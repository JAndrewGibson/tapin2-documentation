
# Tapin2 API Documentation

![Progress](https://geps.dev/progress/37)

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
| POST | [`v2/event/current`](endpoints/event_current_post.md) | 📝 Planned |
| POST | [`v2/event`](endpoints/event_post.md) | 📝 Planned |
| GET | [`v2/venues/{venueId}/events/{eventId}/alcoholcutoff`](endpoints/venues_events_alcoholcutoff.md) | ✅ Documented |
| POST | [`{version}/Event`](endpoints/event_post_version.md) | 📝 Planned |
| GET | [`{version}/Event`](endpoints/event_version.md) | ❌ Blocked (405 Method Not Allowed) |

</details>

<details markdown="1">
<summary><b>📂 Location Endpoints</b></summary>
| Method | Endpoint | Status |
| :--- | :--- | :--- |
| GET | [`v2/locations/{venueId}?includePreorder={includePreorder}`](endpoints/locations_preorder.md) | ✅ Documented |
| GET | [`v2/venues/{venueId}/locations`](endpoints/venue_locations.md) | ✅ Documented |
| GET | [`v2/locations/{venueId}/{includePreorder}`](endpoints/locations.md) | ✅ Documented |
| GET | [`v2/venues/{venueId}/locations/{includePreorder}`](endpoints/venues_locations.md) | ✅ Documented |
| GET | [`v2/venues/{venueId}/sections/{sectionId}/locations`](endpoints/venues_sections_locations.md) | ❌ Blocked (404 Not Found) |
| GET | [`v2/venues/{venueId}/locations/{locationId}/events/{eventId}/alcoholcutoff`](endpoints/venues_locations_events_alcoholcutoff.md) | ✅ Documented |
| POST | [`{version}/Location`](endpoints/location_post_version.md) | 📝 Planned |
| GET | [`{version}/Location`](endpoints/location_version.md) | ❌ Blocked (401 Unauthorized) |

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
| HEAD | [`v1/clear`](endpoints/clear_head_v1.md) | 📝 Planned |
| GET | [`v1/clear`](endpoints/clear_v1.md) | ✅ Documented |
| HEAD | [`v1/clearmenu/{venueId}`](endpoints/clearmenu_head_v1.md) | 📝 Planned |
| GET | [`v1/clearmenu/{venueId}`](endpoints/clearmenu_v1.md) | ✅ Documented |
| GET | [`v1/venues/{venueId}/orders?count={count}`](endpoints/venues_orders_v1.md) | ❌ Blocked (404 Not Found) |
| POST | [`v1/venues/{venueId}/vendors/{locationId}/orders/unprinted`](endpoints/venues_vendors_orders_unprinted_post_v1.md) | 📝 Planned |
| POST | [`v1/venues/{venueId}/locations/{locationId}/orders/unprinted`](endpoints/venues_locations_orders_unprinted_post_v1.md) | 📝 Planned |
| GET | [`v1/venues/{venueId}/orders/{orderId}`](endpoints/venues_orders_v1_2.md) | ❌ Blocked (404 Not Found) |
| PUT | [`v1/venues/{venueId}/orders/{orderId}?printed={printed}&error={error}`](endpoints/venues_orders_put_v1.md) | 📝 Planned |
| POST | [`{version}/Order`](endpoints/order_post_version.md) | 📝 Planned |
| GET | [`{version}/Order`](endpoints/order_version.md) | ✅ Documented |
| POST | [`v2/venues/{venueId}/orders/{eventId}`](endpoints/venues_orders_post.md) | 📝 Planned |
| GET | [`v2/venues/{venueId}/orders/{eventId}`](endpoints/venues_orders.md) | ✅ Documented |
| POST | [`v2/event/orders`](endpoints/event_orders_post.md) | 📝 Planned |
| PUT | [`v2/venues/{venueId}/orders/{orderId}?printed={printed}&error={error}`](endpoints/venues_orders_put.md) | 📝 Planned |
| POST | [`v2/venues/{venueId}/orders/{orderId}/status/{statusId}`](endpoints/venues_orders_status_post.md) | 📝 Planned |
| GET | [`v2/venues/{venueId}/events/{eventId}/orders/{orderId}/refund?userId={userId}&managerPin={managerPin}`](endpoints/venues_events_orders_refund.md) | ❌ Blocked (404 Not Found) |
| GET | [`v2/venues/{venueId}/orders/modified/{fromDate}/{toDate}`](endpoints/venues_orders_modified.md) | ❌ Blocked (Timeout) |
| GET | [`v2/venues/{venueId}/orders/modified/{fromDate}/{fromMins}/{toDate}/{toMins}?addDayToEndOfRange={addDayToEndOfRange}`](endpoints/venues_orders_modified_2.md) | ❌ Blocked (400 Bad Request) |
| GET | [`v2/venues/{venueId}/events/{fromDate}/{toDate}/preorders`](endpoints/venues_events_preorders.md) | ✅ Documented |
| GET | [`v2/venues/{venueId}/events/{fromDate}/{fromMins}/{toDate}/{toMins}/preorders?addDayToEndOfRange={addDayToEndOfRange}`](endpoints/venues_events_preorders_2.md) | ✅ Documented |
| GET | [`v2/venues/{venueId}/events/{eventId}/orders/{seatId}/current`](endpoints/venues_events_orders_current.md) | ✅ Documented |
| POST | [`v2/event/seat/currentorder`](endpoints/event_seat_currentorder_post.md) | 📝 Planned |
| GET | [`v2/venues/{venueId}/events/{eventId}/orders/{orderId}`](endpoints/venues_events_orders.md) | ✅ Documented |
| POST | [`v2/venues/{venueId}/events/{eventId}/orders/{orderId}/message`](endpoints/venues_events_orders_message_post.md) | 📝 Planned |
| POST | [`v2/cart/discount`](endpoints/cart_discount_post.md) | 📝 Planned |
| GET | [`v2/cart/discount/balance`](endpoints/cart_discount_balance.md) | ❌ Blocked (500 Error) |
| POST | [`v2/cart/inventory`](endpoints/cart_inventory_post.md) | 📝 Planned |
| POST | [`v2/cart/prepayment`](endpoints/cart_prepayment_post.md) | 📝 Planned |
| POST | [`v2/paymenttoken`](endpoints/paymenttoken_post.md) | 📝 Planned |
| POST | [`v2/venues/{venueId}/events/{eventId}/orders/{orderId}/pay/applepaysession`](endpoints/venues_events_orders_pay_applepaysession_post.md) | 📝 Planned |
| POST | [`v2/venues/{venueId}/events/{eventId}/orders/{orderId}/pay/applepay`](endpoints/venues_events_orders_pay_applepay_post.md) | 📝 Planned |
| POST | [`v2/cart/closeout`](endpoints/cart_closeout_post.md) | 📝 Planned |
| POST | [`v2/venues/{venueId}/cart/upload`](endpoints/venues_cart_upload_post.md) | 📝 Planned |
| POST | [`{version}/Order2`](endpoints/order2_post_version.md) | 📝 Planned |
| GET | [`{version}/Order2`](endpoints/order2_version.md) | ❌ Blocked (401 Unauthorized) |
| GET | [`v4/venues/{venueId}/events/{eventId}/hawkers/{hawkerId}/orders/small`](endpoints/venues_events_hawkers_orders_small_v4.md) | ✅ Documented |
| GET | [`v4/venues/{venueId}/events/{eventId}/device/{deviceSerial}/orders/small`](endpoints/venues_events_device_orders_small_v4.md) | ❌ Blocked (404 Not Found) |
| GET | [`v4/venues/{venueId}/events/{eventId}/cashiers/{cashierId}/orders/small`](endpoints/venues_events_cashiers_orders_small_v4.md) | ✅ Documented |
| GET | [`v4/venues/{venueId}/orders/small/modified/{fromDate}/{toDate}`](endpoints/venues_orders_small_modified_v4.md) | ❌ Blocked (Timeout) |
| GET | [`v4/venues/{venueId}/orders/small/modified/{fromDate}/{fromMins}/{toDate}/{toMins}?addDayToEndOfRange={addDayToEndOfRange}`](endpoints/venues_orders_small_modified_v4_2.md) | ❌ Blocked (400 Bad Request) |
| GET | [`v4/venues/{venueId}/orders/small/phone/{phone}`](endpoints/venues_orders_small_phone_v4.md) | ❌ Blocked (404 Not Found) |
| GET | [`v4/venues/{venueId}/orders/{orderId}`](endpoints/venues_orders_v4.md) | ✅ Documented |
| POST | [`{version}/Order4`](endpoints/order4_post_version.md) | 📝 Planned |
| GET | [`{version}/Order4`](endpoints/order4_version.md) | ❌ Blocked (401 Unauthorized) |
| POST | [`v4/venues/{venueId}/orders/{orderId}/items/{itemId}/bump/{userId}`](endpoints/venues_orders_items_bump_post_v4.md) | 📝 Planned |
| POST | [`v4/venues/{venueId}/orders/{orderId}/items/multibump/{userId}`](endpoints/venues_orders_items_multibump_post_v4.md) | 📝 Planned |
| POST | [`v4/venues/{venueId}/orders/{orderId}/products/{productId}/vend`](endpoints/venues_orders_products_vend_post_v4.md) | 📝 Planned |
| POST | [`v4/venues/{venueId}/orders/{orderId}/products/{productId}/void/{quantity}`](endpoints/venues_orders_products_void_post_v4.md) | 📝 Planned |
| POST | [`{version}/OrderItem`](endpoints/orderitem_post_version.md) | 📝 Planned |
| GET | [`{version}/OrderItem`](endpoints/orderitem_version.md) | ❌ Blocked (401 Unauthorized) |

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
| GET | [`v2/venues/{venueId}/events/{eventId}/seats/{seatId}/categories`](endpoints/venues_events_seats_categories.md) | ❌ Blocked (500 Error) |
| POST | [`v2/categories`](endpoints/categories_post.md) | 📝 Planned |
| GET | [`v2/venues/{venueId}/events/{eventId}/seats/{seatId}/categories/{categoryId}/products?dob={dob}`](endpoints/venues_events_seats_categories_products.md) | ❌ Blocked (404 Not Found) |
| POST | [`v2/products`](endpoints/products_post.md) | 📝 Planned |
| GET | [`v2/venues/{venueId}/events/{eventId}/locations/{locationId}/products?dob={dob}`](endpoints/venues_events_locations_products.md) | ✅ Documented |
| POST | [`v2/venues/{venueId}/events/{eventId}/locations/{locationId}/products`](endpoints/venues_events_locations_products_post.md) | 📝 Planned |
| POST | [`v2/venues/{venueId}/locations/{locationId}/products/{productId}/active/{isActive}`](endpoints/venues_locations_products_active_post.md) | 📝 Planned |
| POST | [`v2/venues/{venueId}/vendinglocations/{vendingLocationRefId}/products/{productId}/active/{isActive}`](endpoints/venues_vendinglocations_products_active_post.md) | 📝 Planned |
| POST | [`v2/venues/{venueId}/products`](endpoints/venues_products_post.md) | 📝 Planned |
| GET | [`v2/venues/{venueId}/events/{eventId}/section/{sectionId}/row/{row}/expressdelivery`](endpoints/venues_events_section_row_expressdelivery.md) | ✅ Documented |
| GET | [`v2/venues/{venueId}/events/{eventId}/section/{sectionId}/row/{row}/products`](endpoints/venues_events_section_row_products.md) | ✅ Documented |
| GET | [`v2/venues/{venueId}/users/products`](endpoints/venues_users_products.md) | ✅ Documented |
| GET | [`v2/venues/{venueId}/user/{pin}/products`](endpoints/venues_user_products.md) | ❌ Blocked (404 Not Found) |
| POST | [`v2/venues/{venueId}/user/{userId}/products?pin={pin}`](endpoints/venues_user_products_post.md) | 📝 Planned |
| POST | [`{version}/Product`](endpoints/product_post_version.md) | 📝 Planned |
| GET | [`{version}/Product`](endpoints/product_version.md) | ❌ Blocked (401 Unauthorized) |
| GET | [`v4/venues/{venueId}/locations/{locationId}/products/small/modified/{fromDate}/{toDate}`](endpoints/venues_locations_products_small_modified_v4.md) | ✅ Documented |
| GET | [`v4/venues/{venueId}/locations/{locationId}/products/small/modified/{fromDate}/{fromMins}/{toDate}/{toMins}?addDayToEndOfRange={addDayToEndOfRange}`](endpoints/venues_locations_products_small_modified_v4_2.md) | ✅ Documented |
| POST | [`{version}/Product4`](endpoints/product4_post_version.md) | 📝 Planned |
| GET | [`{version}/Product4`](endpoints/product4_version.md) | ❌ Blocked (401 Unauthorized) |

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
| POST | [`v2/venue`](endpoints/venue_post.md) | 📝 Planned |
| POST | [`v2/venues/{venueId}/location?lat={lat}&lng={lng}`](endpoints/venues_location_post.md) | 📝 Planned |
| GET | [`v2/venues/{venueId}/integrations/settings/{locationId}`](endpoints/venues_integrations_settings.md) | ✅ Documented |
| GET | [`v2/venues/{venueId}/service/{serviceId}/options?locationId={locationId}`](endpoints/venues_service_options.md) | ✅ Documented |
| GET | [`v2/venues/{venueId}/service/{serviceId}/options/{locationId}`](endpoints/venues_service_options_2.md) | ✅ Documented |
| GET | [`v2/venues/{venueId}/content/{locationId}`](endpoints/venues_content.md) | ✅ Documented |
| POST | [`{version}/Venue`](endpoints/venue_post_version.md) | 📝 Planned |
| GET | [`{version}/Venue`](endpoints/venue_version.md) | ❌ Blocked (500 Error) |
| POST | [`{version}/VenueGroup`](endpoints/venuegroup_post_version.md) | 📝 Planned |
| GET | [`{version}/VenueGroup`](endpoints/venuegroup_version.md) | ✅ Documented |

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
| **Base** | POST | [`{version}/Base`](endpoints/base_post_version.md) | 📝 Planned |
| **Base** | GET | [`{version}/Base`](endpoints/base_version.md) | ✅ Documented |
| **Error** | POST | [`{version}/Error`](endpoints/error_post_version.md) | 📝 Planned |
| **Error** | GET | [`{version}/Error`](endpoints/error_version.md) | ✅ Documented |
| **Global** | GET | [`v2/global/azurehealthcheck`](endpoints/global_azurehealthcheck.md) | ✅ Documented |
| **Global** | GET | [`v2/global/enums/{enumType}/{asKeyValuePairs}/{nameFirst}`](endpoints/global_enums.md) | ❌ Blocked (404 Not Found) |
| **Global** | POST | [`{version}/Global`](endpoints/global_post_version.md) | 📝 Planned |
| **Global** | GET | [`{version}/Global`](endpoints/global_version.md) | ✅ Documented |
| **Print** | GET | [`v3/venues/{venueId}/vendors/{locationId}/print`](endpoints/venues_vendors_print_v3.md) | ❌ Blocked (404 Not Found) |
| **Print** | GET | [`v3/venues/{venueId}/print/template?templateId={templateId}`](endpoints/venues_print_template_v3.md) | ✅ Documented |
| **Print** | GET | [`v3/venues/{venueId}/print/template/{templateId}`](endpoints/venues_print_template_v3_2.md) | ✅ Documented |
| **Print** | PUT | [`v3/venues/{venueId}/orders/{orderId}/{queueId}?printed={printed}&error={error}`](endpoints/venues_orders_put_v3.md) | 📝 Planned |
| **Print** | POST | [`v3/venues/{venueId}/vendors/{locationId}/print/direct`](endpoints/venues_vendors_print_direct_post_v3.md) | 📝 Planned |
| **Print** | POST | [`v3/venues/{venueId}/locations/{locationId}/print/direct`](endpoints/venues_locations_print_direct_post_v3.md) | 📝 Planned |
| **Print** | POST | [`v3/venues/{venueId}/printers/{deviceId}`](endpoints/venues_printers_post_v3.md) | 📝 Planned |
| **Print** | POST | [`v3/venues/{venueId}/printers/{deviceId}/tabs`](endpoints/venues_printers_tabs_post_v3.md) | 📝 Planned |
| **Print** | POST | [`v3/venues/{venueId}/locations/{locationId}/hawkers/print`](endpoints/venues_locations_hawkers_print_post_v3.md) | 📝 Planned |
| **Print** | POST | [`v3/venues/{venueId}/locations/{locationId}/loadvouchers/print`](endpoints/venues_locations_loadvouchers_print_post_v3.md) | 📝 Planned |
| **Print** | POST | [`v3/venues/{venueId}/locations/{locationId}/devices/{deviceId}/hawkers/print`](endpoints/venues_locations_devices_hawkers_print_post_v3.md) | 📝 Planned |
| **Print** | POST | [`v3/venues/{venueId}/locations/{locationId}/devices/{deviceId}/loadvouchers/print`](endpoints/venues_locations_devices_loadvouchers_print_post_v3.md) | 📝 Planned |
| **Print** | GET | [`v3/venues/{venueId}/local/print?eventId={eventId}&locationId={locationId}&orderId={orderId}&tabId={tabId}&printTemplate={printTemplate}`](endpoints/venues_local_print_v3.md) | ❌ Blocked (500 Error) |
| **Print** | POST | [`v3/venues/{venueId}/local/print/update/{orderId}`](endpoints/venues_local_print_update_post_v3.md) | 📝 Planned |
| **Print** | POST | [`{version}/Print`](endpoints/print_post_version.md) | 📝 Planned |
| **Print** | GET | [`{version}/Print`](endpoints/print_version.md) | ✅ Documented |
| **Report** | GET | [`v1/venues/{venueId}/reports/{reportType}/{fromDate}/{fromMins}/{toDate}/{toMins}?addDayToEndOfRange={addDayToEndOfRange}`](endpoints/venues_reports_v1.md) | ❌ Blocked (500 Error) |
| **Report** | GET | [`v1/venues/{venueId}/reports/{reportType}/events/{eventId}`](endpoints/venues_reports_events_v1.md) | ❌ Blocked (500 Error) |
| **Report** | POST | [`{version}/Report`](endpoints/report_post_version.md) | 📝 Planned |
| **Report** | GET | [`{version}/Report`](endpoints/report_version.md) | ❌ Blocked (401 Unauthorized) |
| **ReportV2** | GET | [`v2/venues/{venueId}/reports/{reportType}/{fromDate}/{toDate}`](endpoints/venues_reports.md) | ❌ Blocked (500 Error) |
| **ReportV2** | GET | [`v2/venues/{venueId}/reports/{reportType}/{fromDate}/{fromMins}/{toDate}/{toMins}?addDayToEndOfRange={addDayToEndOfRange}`](endpoints/venues_reports_2.md) | ❌ Blocked (500 Error) |
| **ReportV2** | GET | [`v2/venues/{venueId}/reports/{reportType}/events/{eventId}`](endpoints/venues_reports_events.md) | ❌ Blocked (500 Error) |
| **ReportV2** | POST | [`{version}/ReportV2`](endpoints/reportv2_post_version.md) | 📝 Planned |
| **ReportV2** | GET | [`{version}/ReportV2`](endpoints/reportv2_version.md) | ❌ Blocked (401 Unauthorized) |
| **Seat** | POST | [`v2/sections`](endpoints/sections_post.md) | 📝 Planned |
| **Seat** | GET | [`v2/venues/{venueId}/events/{eventId}/sections/{sectionId}/rows`](endpoints/venues_events_sections_rows.md) | ❌ Blocked (404 Not Found) |
| **Seat** | POST | [`v2/rows`](endpoints/rows_post.md) | 📝 Planned |
| **Seat** | GET | [`v2/venues/{venueId}/events/{eventId}/sections/{sectionId}/rows/{row}/numbers`](endpoints/venues_events_sections_rows_numbers.md) | ❌ Blocked (404 Not Found) |
| **Seat** | POST | [`v2/seatnumbers`](endpoints/seatnumbers_post.md) | 📝 Planned |
| **Seat** | GET | [`v2/venues/{venueId}/events/{eventId}/seats/{sectionId}/{row}/{seatNumber}`](endpoints/venues_events_seats.md) | ❌ Blocked (404 Not Found) |
| **Seat** | POST | [`v2/seat`](endpoints/seat_post.md) | 📝 Planned |
| **Seat** | POST | [`{version}/Seat`](endpoints/seat_post_version.md) | 📝 Planned |
| **Seat** | GET | [`{version}/Seat`](endpoints/seat_version.md) | ❌ Blocked (405 Method Not Allowed) |
| **Tab** | PUT | [`v2/venues/{venueId}/tabs/{tabId}/printed`](endpoints/venues_tabs_printed_put.md) | 📝 Planned |
| **Tab** | POST | [`{version}/Tab`](endpoints/tab_post_version.md) | 📝 Planned |
| **Tab** | GET | [`{version}/Tab`](endpoints/tab_version.md) | ❌ Blocked (401 Unauthorized) |
| **Tab2** | GET | [`v4/venues/{venueId}/events/{eventId}/tabs`](endpoints/venues_events_tabs_v4.md) | ✅ Documented |
| **Tab2** | GET | [`v4/venues/{venueId}/tabs/modified/{fromDate}/{toDate}`](endpoints/venues_tabs_modified_v4.md) | ✅ Documented |
| **Tab2** | GET | [`v4/venues/{venueId}/tabs/modified/{fromDate}/{fromMins}/{toDate}/{toMins}?addDayToEndOfRange={addDayToEndOfRange}`](endpoints/venues_tabs_modified_v4_2.md) | ✅ Documented |
| **Tab2** | POST | [`{version}/Tab2`](endpoints/tab2_post_version.md) | 📝 Planned |
| **Tab2** | GET | [`{version}/Tab2`](endpoints/tab2_version.md) | ❌ Blocked (401 Unauthorized) |
| **TabSdp** | POST | [`sdp/venues/{venueId}/tabs/print`](endpoints/venues_tabs_print_post_sdp.md) | 📝 Planned |
| **TabSdp** | POST | [`{version}/TabSdp`](endpoints/tabsdp_post_version.md) | 📝 Planned |
| **TabSdp** | GET | [`{version}/TabSdp`](endpoints/tabsdp_version.md) | ✅ Documented |
| **User** | POST | [`{version}/User`](endpoints/user_post_version.md) | 📝 Planned |
| **User** | GET | [`{version}/User`](endpoints/user_version.md) | ❌ Blocked (401 Unauthorized) |
| **YellowDog** | GET | [`yd/venues/{venueId}/orders/modified/{fromDate}/{toDate}`](endpoints/venues_orders_modified_yd.md) | ❌ Blocked (500 Error) |
| **YellowDog** | GET | [`yd/venues/{venueId}/orders/modified/{fromDate}/{fromMins}/{toDate}/{toMins}?addDayToEndOfRange={addDayToEndOfRange}`](endpoints/venues_orders_modified_yd_2.md) | ✅ Documented |
| **YellowDog** | POST | [`{version}/YellowDog`](endpoints/yellowdog_post_version.md) | 📝 Planned |
| **YellowDog** | GET | [`{version}/YellowDog`](endpoints/yellowdog_version.md) | ✅ Documented |

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