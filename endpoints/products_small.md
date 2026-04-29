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
| `title` | String | Name of the product. |
| `fgId` | Integer | Fulfillment Group ID. |
| `price` | Float | Base price of the product. |
| `eventPrice` | Float | Price applicable for the current event. |
| `isActive` | Boolean | Whether the product is available. |
| `modGroups` | Array | List of modifier groups (compact version). |

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
        "title": "Example Item",
        "fgId": 50,
        "price": 10.0,
        "eventPrice": 10.0,
        "isActive": true,
        "modGroups": [
            {
                "id": 201,
                "title": "Options",
                "mods": [
                    { "id": 301, "title": "Option A", "priceDiff": 2.0 },
                    { "id": 302, "title": "Option B", "priceDiff": 0.0 }
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
[← Back to Endpoint Registry](../README.md)
