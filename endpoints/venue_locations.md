# Venue Locations

Retrieve a list of all service locations (stands, suites, carts) within a venue.

- **Endpoint**: `v2/venues/{venueId}/locations`
- **Method**: `GET`
- **Authentication**: Required (`Key` header)

## Parameters

| Name | Type | Located In | Description |
| :--- | :--- | :--- | :--- |
| `venueId` | Integer | Path | The unique identifier for the venue. |

## Response Structure

Returns an array of location objects.

| Field | Type | Description |
| :--- | :--- | :--- |
| `id` | Integer | Unique identifier for the location. |
| `title` | String | Name of the location (e.g., "Main Grill", "Suite 101"). |
| `description`| String | Detailed description of the location. |
| `section` | String | Seating section associated with the location. |
| `imageUrl` | String | Primary image URL for the location. |
| `isDelivery` | Boolean | Whether this location supports delivery service. |
| `isPickup` | Boolean | Whether this location supports pickup service. |
| `isHawker` | Boolean | Whether this location is a mobile hawker. |
| `isActive` | Boolean | Whether the location is currently available in the system. |
| `isPaused` | Boolean | Whether service is temporarily paused for this location. |
| `pauseExpiration`| String | ISO timestamp when the current pause expires. |
| `waitTime` | String | Human-readable wait time string (e.g., "approx wait 0-5 mins"). |
| `orderingEnabled`| Boolean | Global toggle for ordering at this location. |

## Example Response (Sanitized)

```json
[
    {
        "id": 12345,
        "title": "Example Stand 101",
        "description": "Main Level Concessions",
        "section": "101",
        "imageUrl": "https://storage.tapin2.co/images/example_stand.png",
        "isDelivery": false,
        "isPickup": true,
        "isHawker": false,
        "isActive": true,
        "isPaused": false,
        "pauseExpiration": null,
        "waitTime": "approx wait 5-10 mins",
        "orderingEnabled": true
    },
    {
        "id": 12346,
        "title": "Example Suite 202",
        "isDelivery": true,
        "isPickup": false,
        "isHawker": false,
        "isActive": true,
        "isPaused": false,
        "waitTime": "",
        "orderingEnabled": true
    }
]
```

## Venue-Specific Notes

- **Suite-based Venues**: Often have locations representing specific service carts or "Day Of" ordering windows. Delivery is almost always `true`.
- **Concessions-based Venues**: Locations represent physical stands. `isPickup` is the primary service method. Closed locations will often have `isActive: false` or specific text in the `title`.

---
[← Back to Endpoint Registry](../README.md)
