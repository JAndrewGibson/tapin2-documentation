# Tab Details

Retrieve the full state of a specific customer tab, including all associated orders, payments, and balance information. This is primarily used in Suite and Restaurant environments.

- **Endpoint**: `v4/venues/{venueId}/tabs/{tabId}`
- **Method**: `GET`
- **Authentication**: Required (`Key` header)

## Parameters

| Name | Type | Located In | Description |
| :---| :---| :---| :---|
| `venueId` | Integer | Path | The unique identifier for the venue. |
| `tabId` | Integer | Path | The unique identifier for the tab. |

## Response Structure

Returns a comprehensive tab object.

| Field | Type | Description |
| :---| :---| :---|
| `id` | Integer | Unique identifier for the tab. |
| `venueId` | Integer | ID of the venue. |
| `locationId` | Integer | ID of the location where the tab was opened. |
| `title` | String | The name or title of the tab (e.g., "Suite 101 - Gibson"). |
| `status` | Integer | Numerical status code (e.g., 1=Open, 2=Closed). |
| `orders` | Array | List of all order objects associated with this tab. |
| `payments` | Array | List of payment transactions applied to the tab. |
| `createDate` | String | Timestamp when the tab was opened. |
| `modifyDate` | String | Timestamp of the last update. |
| `closeDate` | String | Timestamp when the tab was finalized. |

### Order Object Schema (Nested in `orders`)

Contains the details of an individual order within the tab.

| Field | Type | Description |
| :---| :---| :---|
| `id` | Integer | Unique identifier for the order. |
| `status` | Integer | Order status (e.g., 1=Pending, 2=Fulfilled). |
| `totalGross` | Float | The total amount for this specific order. |
| `items` | [Array](../models/item.md) | List of product items included in this order. |

## Example Response (Sanitized)

```json
{
    "id": 12345,
    "venueId": 1408,
    "locationId": 101,
    "title": "Example Suite Tab",
    "status": 1,
    "createDate": "04/29/2026 10:00 AM",
    "modifyDate": "04/29/2026 11:30 AM",
    "closeDate": null,
    "orders": [
        {
            "id": 98765,
            "status": 2,
            "totalGross": 150.0,
            "items": [
                {
                    "id": 1,
                    "product": "Premium Beer Case",
                    "quantity": 1,
                    "pricePer": 150.0,
                    "total": 150.0
                }
            ]
        }
    ],
    "payments": [
        {
            "id": 4,
            "type": 1,
            "amount": 10.6,
            "date": "01/19/2017 7:21 AM"
        }
    ]
}
```

## Venue-Specific Notes

- **Suite Management**: In suite environments, a single tab often spans multiple "Order Rounds" (e.g., Pre-stock, Game Day 1st Round, etc.).
- **Payments**: A tab can have multiple partial payments or "Split Checks" represented in the `payments` array.

---
[🔗 View Original Documentation](https://api.tapin2.co/Help/Api/GET-v4-venues-venueId-tabs-tabId)

[← Back to Endpoint Registry](../README.md)
