# Unprinted Orders

Retrieve a list of orders that have been placed but not yet printed or fulfilled at a venue. This endpoint is primarily used by kitchen and fulfillment terminals to track pending activity.

- **Endpoint**: `v2/venues/{venueId}/orders/unprinted`
- **Method**: `GET`
- **Authentication**: Required (`Key` header)

## Parameters

| Name | Type | Located In | Description |
| :--- | :--- | :--- | :--- |
| `venueId` | Integer | Path | The unique identifier for the venue. |

## Response Structure

Returns an array of complex order objects.

| Field | Type | Description |
| :--- | :--- | :--- |
| `id` | Integer | Unique identifier for the order. |
| `idLast3` | String | Last 3 digits of the order ID (often used as a display number). |
| `venueId` | Integer | The venue where the order was placed. |
| `eventId` | Integer | The specific event associated with the order. |
| `locationId` | Integer | The service location (stand/bar) for the order. |
| `orderDate` | String | Timestamp of when the order was placed (**UTC**). |
| `saleDate` | String | Timestamp of the financial transaction (**UTC**). |
| `subtotalGross` | Float | Total before discounts and taxes. |
| `discount` | Object | Details of applied discounts (code, description, amount). |
| `totalGross` | Float | Final total amount. |
| `isPaidInFull` | Boolean | Whether the transaction has been completed. |
| `items` | Array | List of products in the order. |
| `distinctLocations`| Array | List of unique locations involved in the order. |
| `receiptUrl` | String | Link to the digital receipt. |

### Item Object Structure

| Field | Type | Description |
| :--- | :--- | :--- |
| `id` | Integer | Unique identifier for the line item. |
| `quantity` | Integer | Number of units purchased. |
| `pricePer` | Float | Price per unit. |
| `subtotal` | Float | Total for this line item. |
| `product` | Object | Full product details (title, imageUrl, price, etc.). |

## Example Response (Sanitized)

```json
[
    {
        "id": 11090001,
        "idLast3": "001",
        "venueId": 451,
        "eventId": 188841,
        "locationId": 11829,
        "orderDate": "04/30/2026 6:45 PM",
        "saleDate": "04/30/2026 6:45 PM",
        "subtotalGross": 9.0,
        "discount": {
            "code": "DISCOUNT_ABC",
            "description": "EXAMPLE DISCOUNT",
            "amount": 1.0,
            "amountString": "100%"
        },
        "totalGross": 0.0,
        "isPaidInFull": true,
        "items": [
            {
                "id": 94257760,
                "quantity": 1,
                "pricePer": 9.0,
                "subtotal": 9.0,
                "product": {
                    "id": 298098,
                    "title": "Example Item",
                    "price": 9.0
                }
            }
        ],
        "receiptUrl": "https://mobile.tapin2.co/r/EXAMPLE_TOKEN"
    }
]
```

## Implementation Notes

- **Timezones**: Unlike the Events endpoints which return local venue time, the Order endpoints typically return timestamps in **UTC**. Developers should localize these based on the `venue.timeZoneInfo` provided in the response.
- **Empty State**: If no unprinted orders exist, the endpoint returns an empty array `[]`.
- **Fulfillment**: Once an order is marked as "Printed" or "Fulfilled" in the system, it will no longer appear in this list.

---
[← Back to Endpoint Registry](../README.md)
