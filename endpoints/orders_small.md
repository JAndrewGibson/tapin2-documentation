# Orders (Small)

Retrieve a compact list of orders for a specific event. This endpoint provides flattened order objects with essential financial totals and a simplified item list, optimized for high-performance dashboarding and quick lookup.

- **Endpoint**: `v4/venues/{venueId}/events/{eventId}/orders/small`
- **Method**: `GET`
- **Authentication**: Required (`Key` header)

## Parameters

| Name | Type | Located In | Description |
| :---| :---| :---| :---|
| `venueId` | Integer | Path | The unique identifier for the venue. |
| `eventId` | Integer | Path | The unique identifier for the event. |

## Response Structure

Returns an array of "small" order objects.

| Field | Type | Description |
| :---| :---| :---|
| `id` | Integer | Unique identifier for the order. |
| `venueId` | Integer | The venue ID. |
| `venueName` | String | Display name of the venue. |
| `eventId` | Integer | The event ID. |
| `eventName` | String | Name of the event. |
| `status` | Integer | Order status code (e.g., `2` for Paid/Complete). |
| `service` | Integer | Service method code. |
| `deviceId` | String | Hardware ID of the device that placed the order. |
| `deviceName` | String | Human-readable name of the device. |
| `orderDate` | String | Timestamp of order placement (**UTC**). |
| `saleDate` | String | Timestamp of transaction completion (**UTC**). |
| `subtotalGross`| Float | Gross total before discounts. |
| `discountGross`| Float | Total discount amount applied. |
| `discountCode` | String | The coupon or manager discount code used. |
| `totalGross` | Float | Final total charged to the customer. |
| `items` | [Array](../models/item.md) | Simplified list of items in the order. |

### Small Item Object

| Field | Type | Description |
| :---| :---| :---|
| `id` | Integer | Unique identifier for the line item. |
| `location` | String | Name of the location where the item was served. |
| `productId` | Integer | ID of the product. |
| `product` | String | **Flattened Title** of the product (not a full object). |
| `category` | String | Name of the product category. |
| `quantity` | Integer | Number of units. |
| `pricePer` | Float | Unit price. |
| `total` | Float | Line item total. |
| `modifiers` | [Array](../models/modifier.md) | List of modifiers applied to the item. |

### Modifier Object

| Field | Type | Description |
| :---| :---| :---|
| `id` | Integer | Unique identifier for the modifier. |
| `title` | String | Display name of the modifier. |
| `priceDiff` | Float | The price adjustment applied by this modifier. |
| `quantity` | Integer | Quantity of the modifier applied. |


## Example Response (Sanitized)

```json
[
    {
        "id": 57036979,
        "venueId": 451,
        "venueName": "Example Venue",
        "eventId": 188841,
        "eventName": "EXAMPLE_EVENT",
        "status": 2,
        "orderDate": "04/30/2026 6:45 PM",
        "subtotalGross": 9.0,
        "discountGross": 9.0,
        "discountCode": "MANAGER_DISC",
        "totalGross": 0.0,
        "items": [
            {
                "id": 94259931,
                "location": "Example Bar",
                "productId": 362622,
                "product": "Example Product",
                "category": "BEER",
                "quantity": 1,
                "pricePer": 25.0,
                "total": 0.0,
                "modifiers": [
                    {
                        "id": 1833730,
                        "title": "MAKE IT A MICHELADA",
                        "priceDiff": 7.0,
                        "quantity": 1
                    }
                ]
            }
        ]
    }
]
```

## Implementation Notes

- **Payload Optimization**: This endpoint is significantly faster than the standard orders endpoint as it avoids deep nesting of product, modifier, and location objects.
- **Timezones**: Like other order endpoints, timestamps are returned in **UTC**.

---
[🔗 View Original Documentation](https://api.tapin2.co/Help/Api/GET-v4-venues-venueId-events-eventId-orders-small)

[← Back to Endpoint Registry](../README.md)
