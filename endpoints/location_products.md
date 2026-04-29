# Location Products

Retrieve all products associated with a specific location, including category and fulfillment group mapping.

- **Endpoint**: `v2/venues/{venueId}/locations/{locationId}/products`
- **Method**: `GET`
- **Authentication**: Required (`Key` header)

## Parameters

| Name | Type | Located In | Description |
| :--- | :--- | :--- | :--- |
| `venueId` | Integer | Path | The unique identifier for the venue. |
| `locationId` | Integer | Path | The unique identifier for the location. |

## Response Structure

Returns an array of location-product mapping objects.

| Field | Type | Description |
| :--- | :--- | :--- |
| `product` | Object | Full product configuration (see [products_venue.md](products_venue.md)). |
| `productId` | Integer | Unique identifier for the product. |
| `location` | Object | Details of the assigned location. |
| `locationId` | Integer | ID of the assigned location. |
| `category` | Object | Details of the product category. |
| `categoryId` | Integer | ID of the product category. |
| `fulfillmentGroup`| Object | Details of the fulfillment group (e.g., "ALCOHOL"). |
| `fulfillmentGroupId`| Integer | ID of the fulfillment group. |
| `menuId` | Integer | ID of the menu this product-location mapping belongs to. |
| `orderId` | Integer | Display order for the product within its category. |
| `isActive` | Boolean | Whether the product is active at this location. |
| `isVisible` | Boolean | Whether this product should be shown in the UI. |

### Category Object

| Field | Type | Description |
| :--- | :--- | :--- |
| `id` | Integer | ID of the category. |
| `title` | String | Name of the category (e.g., "Beer", "Snacks"). |

## Example Response (Sanitized)

```json
[
    {
        "productId": 1001,
        "locationId": 401,
        "categoryId": 501,
        "fulfillmentGroupId": 201,
        "isActive": true,
        "isVisible": true,
        "orderId": 10,
        "product": {
            "id": 1001,
            "title": "Example Beer",
            "price": 12.0
        },
        "location": {
            "id": 401,
            "title": "Main Bar",
            "isPaused": false
        },
        "category": {
            "id": 60,
            "title": "BEER"
        },
        "fulfillmentGroup": {
            "id": 70,
            "title": "ALCOHOL"
        },
        "isActive": true,
        "isVisible": true
    }
]
```

## Venue-Specific Notes

- **Menu Mapping**: Unlike the venue-wide product list, this endpoint respects location-specific menus and exclusions.
- **Fulfillment**: The `fulfillmentGroup` is used by the Tapin2 printer and KDS (Kitchen Display System) to route items correctly.

---
[← Back to Endpoint Registry](../README.md)
