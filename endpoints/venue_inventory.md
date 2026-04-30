# Venue Inventory

Retrieve real-time inventory and stock levels for all products in a venue.

- **Endpoint**: `v2/venues/{venueId}/inventory`
- **Method**: `GET`
- **Authentication**: Required (`Key` header)

## Parameters

| Name | Type | Located In | Description |
| :---| :---| :---| :---|
| `venueId` | Integer | Path | The unique identifier for the venue. |

## Response Structure

Returns an array of inventory objects. Each object contains the product metadata and its current stock status.

| Field | Type | Description |
| :---| :---| :---|
| `id` | Integer | Unique identifier for the inventory record. |
| `productId` | Integer | ID of the associated product. |
| `product` | Object | Full product configuration details (see [products_venue.md](products_venue.md) for schema). |
| `modifier` | String | (Optional) Modifier string for the item. |
| `upc` | String | (Optional) UPC for the item. |
| `defaultQuantity`| Integer | Initial/Default quantity for the item. |
| `currentQuantity`| Integer | Current stock level (null if not tracked). |

## Example Response (Sanitized)

```json
[
    {
        "id": 5001,
        "productId": 1001,
        "product": {
            "id": 1001,
            "title": "Example Product",
            "price": 10.0
        },
        "modifier": "",
        "upc": "123456789",
        "defaultQuantity": 100,
        "currentQuantity": 85
    }
]
```

## Venue-Specific Notes

- **Concessions-based Venues**: Frequently used for real-time "Sold Out" status. If `currentQuantity` is 0, the item should be considered unavailable.
- **Data Volume**: This endpoint returns the **full** product object for every item, making the response significantly larger than the standard products endpoint. Use with caution.

---
[🔗 View Original Documentation](https://api.tapin2.co/Help/Api/GET-v2-venues-venueId-inventory)

[← Back to Endpoint Registry](../README.md)
