# Get Products by Venue

Retrieve a list of all products configured for a specific venue. This is the primary endpoint for populating menus and inventory lists.

- **Endpoint**: `v2/venues/{venueId}/products`
- **Method**: `GET`
- **Authentication**: Required (`Key` header)

## Parameters

| Name | Type | Located In | Description |
| :--- | :--- | :--- | :--- |
| `venueId` | Integer | Path | The unique identifier for the venue. |

## Response Structure

Returns an array of product objects.

| Field | Type | Description |
| :--- | :--- | :--- |
| `id` | Integer | Unique identifier for the product. |
| `title` | String | Public name of the product. |
| `description` | String | Long-form description (supports HTML-encoded characters). |
| `price` | Float | Base price of the product. |
| `isAlcohol` | Boolean | Flag indicating if the item contains alcohol. |
| `isActive` | Boolean | Whether the product is currently available for purchase. |
| `categoryId` | Integer | ID of the parent category. |
| `imageUrl` | String | URL to the product image asset. |
| `productGroups` | Array | (Suites/Combos) List of component groups for packages. |
| `priceLevels` | Array | List of available price levels for different event types. |
| `modifierGroups`| Array | List of customization groups (e.g., "Add Ons"). |

### Product Group Object (Packages/Combos)

| Field | Type | Description |
| :--- | :--- | :--- |
| `id` | Integer | Unique ID for the component group. |
| `title` | String | Name of the choice group (e.g., "Appetizer Selection"). |

## Example Response (Suite-based Venue - Package)

```json
{
    "id": 1001,
    "title": "Example Package",
    "price": 500.0,
    "isAlcohol": false,
    "productGroups": [
        {
            "id": 1,
            "title": "Main Selection"
        },
        {
            "id": 2,
            "title": "Side Selection"
        }
    ],
    "priceLevels": [
        { "id": 10, "title": "Standard Pricing" }
    ]
}
```

## Venue-Specific Notes

- **Suite-based Venues**: Frequently returns products with `productGroups`, representing **Packages** where the user must select multiple items (e.g., "Main Selection", "Side Selection").
- **Concessions-based Venues**: Typically returns standard items with generic `imageUrl` and `priceLevels` corresponding to event types (e.g., "Game Day" vs "Concert").

---
[← Back to Endpoint Registry](README.md)
