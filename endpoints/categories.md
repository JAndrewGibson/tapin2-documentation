# Location Categories

Retrieve all product categories available at a specific location.

- **Endpoint**: `v2/venues/{venueId}/locations/{locationId}/categories`
- **Method**: `GET`
- **Authentication**: Required (`Key` header)

## Parameters

| Name | Type | Located In | Description |
| :--- | :--- | :--- | :--- |
| `venueId` | Integer | Path | The unique identifier for the venue. |
| `locationId` | Integer | Path | The unique identifier for the location. |

## Response Structure

Returns an array of category objects.

| Field | Type | Description |
| :--- | :--- | :--- |
| `id` | Integer | Unique identifier for the category. |
| `title` | String | Name of the category (e.g., "BEER", "FOOD"). |
| `imageUrl` | String | URL for the category icon or image. |
| `isActive` | Boolean | Whether the category is currently enabled. |
| `orderId` | Integer | The display order for the UI. |
| `posRefId` | String | External reference ID for POS integration. |
| `commissionRate` | Float | Applicable commission rate for this category. |
| `commissionFlat` | Float | Flat commission fee for this category. |
| `subcategories` | Array | List of nested subcategories. |

## Example Response (Sanitized)

```json
[
    {
        "id": 6001,
        "title": "EXAMPLE_CATEGORY_A",
        "imageUrl": "https://storage.tapin2.co/images/example_a.jpg",
        "isActive": true,
        "orderId": 1,
        "posRefId": "POS-123",
        "commissionRate": 0.0,
        "commissionFlat": 0.0,
        "subcategories": []
    },
    {
        "id": 6002,
        "title": "EXAMPLE_CATEGORY_B",
        "imageUrl": "",
        "isActive": true,
        "orderId": 2,
        "posRefId": null,
        "commissionRate": 0.0,
        "commissionFlat": 0.0,
        "subcategories": []
    }
]
```

## Venue-Specific Notes

- **Subcategories**: Some complex menus use subcategories to further organize products (e.g., "Craft Beer" under "BEER").
- **Display Priority**: The `orderId` field should be used to sort categories in the user interface. Lower numbers typically indicate higher priority.

---
[🔗 View Original Documentation](https://api.tapin2.co/Help/Api/GET-v2-venues-venueId-locations-locationId-categories)

[← Back to Endpoint Registry](../README.md)
