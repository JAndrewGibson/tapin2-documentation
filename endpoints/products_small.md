# Products Small (v4)

Retrieve a lightweight list of products for a specific location, optimized for mobile or bandwidth-constrained clients.

- **Endpoint**: `v4/venues/{venueId}/locations/{locationId}/products/small`
- **Method**: `GET`
- **Authentication**: Required (`Key` header)

## Parameters

| Name | Type | Located In | Description |
| :--- | :--- | :--- | :--- |
| `venueId` | Integer | Path | The unique identifier for the venue. |
| `locationId` | Integer | Path | The unique identifier for the location. |

## Response Structure

Returns an array of compact product objects.

| Field | Type | Description |
| :--- | :--- | :--- |
| `id` | Integer | Unique identifier for the product. |
| `title` | String | Public name of the product. |
| `fgId` | Integer | Fulfillment Group ID (e.g., KITCHEN=1, BAR=2). |
| `price` | Float | Standard base price. |
| `eventPrice`| Float | Current price for the active event context. |
| `isActive` | Boolean | Whether the product is currently active. |
| `modifyDate` | String | Timestamp of the last configuration change. |
| `upc` | String | Barcode/UPC for the item. |
| `modGroups` | Array | List of simplified modifier group objects. |

### Compact Modifier Group

| Field | Type | Description |
| :--- | :--- | :--- |
| `id` | Integer | ID of the modifier group. |
| `title` | String | Name of the group (e.g., "Size", "Add-ons"). |
| `mods` | Array | List of compact modifier objects. |

### Compact Modifier

| Field | Type | Description |
| :--- | :--- | :--- |
| `id` | Integer | ID of the modifier. |
| `title` | String | Name of the modifier (e.g., "Large"). |
| `priceDiff` | Float | Price adjustment for selecting this modifier. |

## Example Response (Sanitized)

```json
[
    {
    "id": 1001,
    "title": "Example Small Product",
    "fgId": 501,
    "price": 10.0,
    "eventPrice": 12.0,
    "modifyDate": "2026-04-29 12:00:00",
    "isActive": true,
    "upc": "123456789",
    "modGroups": [
        {
            "id": 201,
            "title": "Add-Ons",
            "mods": [
                {
                    "id": 3001,
                    "title": "Extra Cheese",
                    "priceDiff": 1.50,
                    "isActive": true
                }
            ]
        }
    ]
}
]
```

## Venue-Specific Notes

- **Optimized for Mobile**: Use this endpoint instead of `v2/venues/{venueId}/products` when building mobile applications to reduce payload size.
- **Missing Data**: This endpoint does not include `productGroups` (Packages) or full image URLs. It is primarily for simple concessions ordering.

---
[🔗 View Original Documentation](https://api.tapin2.co/Help/Api/GET-v4-venues-venueId-locations-locationId-products-small)

[← Back to Endpoint Registry](../README.md)
