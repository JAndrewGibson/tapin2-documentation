# Venue Inventory

Retrieve real-time inventory and stock levels for all products in a venue.

- **Endpoint**: `v2/venues/{venueId}/inventory`
- **Method**: `GET`
- **Authentication**: Required (`Key` header)

## Parameters

| Name | Type | Located In | Description |
| :--- | :--- | :--- | :--- |
| `venueId` | Integer | Path | The unique identifier for the venue. |

## Response Structure

Returns an array of inventory objects. Each object contains the product metadata and its current stock status.

| Field | Type | Description |
| :--- | :--- | :--- |
| `product` | Object | Full product metadata (see [products_venue.md](products_venue.md)). |
| `currentQuantity` | Integer | The current number of items remaining in stock. Returns `null` if inventory tracking is disabled. |
| `defaultQuantity` | Integer | The starting stock level for the current event/period. |
| `upc` | String | Barcode associated with the specific inventory item. |

## Example Response (Sanitized)

```json
[
    {
        "product": {
            "id": 1001,
            "title": "Example Item",
            "price": 10.0
        },
        "currentQuantity": 50,
        "defaultQuantity": 100,
        "upc": "1234567890"
    }
]
```

## Venue-Specific Notes

- **Concessions-based Venues**: Frequently used for real-time "Sold Out" status. If `currentQuantity` is 0, the item should be considered unavailable.
- **Data Volume**: This endpoint returns the **full** product object for every item, making the response significantly larger than the standard products endpoint. Use with caution.

---
[← Back to Endpoint Registry](../README.md)
