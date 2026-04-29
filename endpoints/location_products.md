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
| `product` | Object | Full product metadata (see [products_venue.md](products_venue.md)). |
| `location` | Object | Full location metadata (see [venue_locations.md](venue_locations.md)). |
| `category` | Object | Category mapping for this product at this location. |
| `fulfillmentGroup` | Object | The group responsible for fulfilling this product (e.g., "Kitchen", "Bar"). |
| `isActive` | Boolean | Whether this product is currently active at this location. |
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
        "product": {
            "id": 1001,
            "title": "Example Beer",
            "price": 12.0
        },
        "locationId": 5001,
        "location": {
            "id": 5001,
            "title": "Example Stand"
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
