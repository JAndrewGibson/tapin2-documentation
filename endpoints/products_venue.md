# Get Products by Venue

Retrieve a list of all products configured for a specific venue. This is the primary endpoint for populating menus and inventory lists.

- **Endpoint**: `v2/venues/{venueId}/products`
- **Method**: `GET`
- **Authentication**: Required (`Key` header)

## Parameters

| Name | Type | Located In | Description |
| :---| :---| :---| :---|
| `venueId` | Integer | Path | The unique identifier for the venue. |

## Response Structure

Returns an array of product objects.

| Field | Type | Description |
| :---| :---| :---|
| `id` | Integer | Unique identifier for the product. |
| `title` | String | Public name of the product. |
| `internalTitle`| String | Internal/Admin name of the product. |
| `sku` | String | Stock Keeping Unit identifier. |
| `posId` | String | External ID for POS mapping. |
| `description` | String | Long-form description. |
| `price` | Float | Base price of the product. |
| `calories` | Integer | Calorie count for the item. |
| `isAlcohol` | Boolean | Flag indicating if the item contains alcohol. |
| `isActive` | Boolean | Whether the product is currently available. |
| `categoryId` | Integer | ID of the parent category. |
| `imageUrl` | String | URL to the product image asset. |
| `showInSuite` | Boolean | Whether the product is visible for Suite service. |
| `showInMobile` | Boolean | Whether the product is visible for Mobile ordering. |
| `showInKiosk` | Boolean | Whether the product is visible for Kiosk ordering. |
| `productGroups` | Array | (Packages/Combos) List of component groups. |
| `priceLevels` | Array | List of available price levels. |
| `modifierGroups`| Array | List of customization groups (e.g., "Add Ons"). |

### Product Group Object (Packages/Combos)

| Field | Type | Description |
| :---| :---| :---|
| `id` | Integer | Unique ID for the component group. |
| `title` | String | Name of the choice group (e.g., "Appetizer Selection"). |

## Example Response (Suite-based Venue - Package)

```json
{
    "id": 1001,
    "title": "Example Package",
    "internalTitle": "SUITE_PKG_EX",
    "sku": "PKG-001",
    "posId": "1001",
    "price": 500.0,
    "calories": 1200,
    "isAlcohol": false,
    "isActive": true,
    "categoryId": 501,
    "imageUrl": "https://storage.tapin2.co/images/example_pkg.jpg",
    "showInSuite": true,
    "showInMobile": false,
    "showInKiosk": false,
    "productGroups": [
        {
            "id": 1,
            "title": "Main Selection",
            "minChoices": 1,
            "maxChoices": 1,
            "products": []
        }
    ],
    "priceLevels": [
        { "id": 10, "title": "Standard Pricing", "price": 500.0 }
    ],
    "modifierGroups": []
}
```

## Venue-Specific Notes

- **Suite-based Venues**: Frequently returns products with `productGroups`, representing **Packages** where the user must select multiple items (e.g., "Main Selection", "Side Selection").
- **Concessions-based Venues**: Typically returns standard items with generic `imageUrl` and `priceLevels` corresponding to event types (e.g., "Game Day" vs "Concert").



## Related Endpoints

- [Venue Inventory](venue_inventory.md)
- [Location Products](location_products.md)

---
[🔗 View Original Documentation](https://api.tapin2.co/Help/Api/GET-v2-venues-venueId-products)

[← Back to Endpoint Registry](../README.md)
