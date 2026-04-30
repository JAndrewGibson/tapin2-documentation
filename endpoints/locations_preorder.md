# Locations with Preorder

Retrieve a list of service locations, with an option to include locations configured for preordering.

- **Endpoint**: `v2/locations/{venueId}?includePreorder={includePreorder}`
- **Method**: `GET`
- **Authentication**: Required (`Key` header)

## Parameters

| Name | Type | Located In | Description |
| :---| :---| :---| :---|
| `venueId` | Integer | Path | The unique identifier for the venue. |
| `includePreorder` | Boolean | Query | If `true`, includes locations specifically designated for preorder workflows. |

## Response Structure

Returns an array of location objects. This structure is identical to the [Venue Locations](venue_locations.md) endpoint.

| Field | Type | Description |
| :---| :---| :---|
| `id` | Integer | Unique identifier for the location. |
| `title` | String | Name of the location. |
| `description`| String | Detailed description of the location. |
| `section` | String | Seating section associated with the location. |
| `imageUrl` | String | Primary image URL for the location. |
| `imageUrlTerminal`| String | Image URL for terminal/POS display. |
| `isDelivery` | Boolean | Whether this location supports delivery service. |
| `isPickup` | Boolean | Whether this location supports pickup service. |
| `isHawker` | Boolean | Whether this location is a mobile hawker. |
| `isActive` | Boolean | Whether the location is currently available. |
| `isPaused` | Boolean | Whether service is temporarily paused. |
| `pauseExpiration`| String | ISO timestamp when the current pause expires. |
| `waitTime` | String | Human-readable wait time string. |
| `orderingEnabled`| Boolean | Global toggle for ordering at this location. |

## Example Response (Sanitized - Preorder Filter)

```json
[
    {
        "id": 12345,
        "title": "Example Preorder Stand",
        "description": "Premium Level Concessions",
        "section": "200",
        "imageUrl": "https://storage.tapin2.co/images/example_pre.png",
        "imageUrlTerminal": "https://storage.tapin2.co/images/example_pos.png",
        "isDelivery": false,
        "isPickup": true,
        "isHawker": false,
        "isActive": true,
        "isPaused": false,
        "pauseExpiration": null,
        "waitTime": "approx wait 0-5 mins",
        "orderingEnabled": true
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
[🔗 View Original Documentation](https://api.tapin2.co/Help/Api/GET-v2-locations-venueId)

[← Back to Endpoint Registry](../README.md)
