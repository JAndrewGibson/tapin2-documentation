# Locations with Preorder

Retrieve a list of service locations, with an option to include locations configured for preordering.

- **Endpoint**: `v2/locations/{venueId}?includePreorder={includePreorder}`
- **Method**: `GET`
- **Authentication**: Required (`Key` header)

## Parameters

| Name | Type | Located In | Description |
| :--- | :--- | :--- | :--- |
| `venueId` | Integer | Path | The unique identifier for the venue. |
| `includePreorder` | Boolean | Query | If `true`, includes locations specifically designated for preorder workflows. |

## Response Structure

Returns an array of location objects. This structure is identical to the [Venue Locations](venue_locations.md) endpoint.

| Field | Type | Description |
| :--- | :--- | :--- |
| `id` | Integer | Unique identifier for the location. |
| `title` | String | Name of the location. |
| `isDelivery` | Boolean | Whether this location supports delivery. |
| `isPickup` | Boolean | Whether this location supports pickup. |
| `isActive` | Boolean | Whether the location is currently available. |

## Example Response (Sanitized - Preorder Filter)

```json
[
    {
        "id": 11111,
        "title": "EXAMPLE_CATEGORY",
        "isDelivery": false,
        "isPickup": true,
        "isActive": true
    },
    {
        "id": 22222,
        "title": "Preorder Window",
        "isDelivery": true,
        "isPickup": false,
        "isActive": true
    }
]
```

## Venue-Specific Notes

- **Preorder Flags**: Locations specifically designated for advanced ordering often have different service windows and lead times compared to immediate fulfillment locations.
- **Suite-based Venues**: Frequently use this to separate "Day Of" ordering from "Advanced Preorder" ordering windows.

---
[← Back to Endpoint Registry](README.md)
