# GET v2/venues/{venueId}/locations/{includePreorder}

Retrieve details for the specified endpoint.

- **Endpoint**: `v2/venues/{venueId}/locations/{includePreorder}`
- **Method**: `GET`
- **Authentication**: Required (`Key` header)

## Parameters

| Name | Type | Located In | Description |
| :---| :---| :---| :---|
| `venueId` | Integer | Path | The parameter in path. |
| `includePreorder` | Integer | Path | The parameter in path. |


## Response Structure

| Field | Type | Description |
| :---| :---| :---|
| `[].description` | String |  |
| `[].section` | String |  |
| `[].imageUrl` | String | URL link to the resource. |
| `[].imageUrlMobile` | String | URL link to the resource. |
| `[].imageUrlTerminal` | String | URL link to the resource. |
| `[].imageUrlPreorder` | String | URL link to the resource. |
| `[].imageUrlMenuPortrait` | String | URL link to the resource. |
| `[].imageUrlMenuLandscape` | String | URL link to the resource. |
| `[].orderingEnabled` | Boolean |  |
| `[].isActive` | Boolean | Indicates whether the record is currently active. |
| `[].pauseExpiration` | String |  |
| `[].isHawker` | Boolean |  |
| `[].orderId` | Integer | Unique identifier for the order. |
| `[].isDelivery` | Boolean |  |
| `[].isPickup` | Boolean |  |
| `[].waitTime` | String | Timestamp in standard formatting. |
| `[].availablePickupTimes` | Null | Timestamp in standard formatting. |
| `[].isPaused` | Boolean |  |
| `[].id` | Integer | Unique identifier for the record. |
| `[].title` | String | The name or title of the title. |

## Example Response (Sanitized)

```json
[
    {
        "description": "Example Title",
        "section": "",
        "imageUrl": "https://storage.tapin2.co/images/example.jpg",
        "imageUrlMobile": "",
        "imageUrlTerminal": "Example Venue",
        "imageUrlPreorder": "",
        "imageUrlMenuPortrait": "",
        "imageUrlMenuLandscape": "",
        "orderingEnabled": true,
        "isActive": false,
        "pauseExpiration": "02/22/2026 8:16 AM",
        "isHawker": false,
        "orderId": 40,
        "isDelivery": false,
        "isPickup": true,
        "waitTime": "approx wait 0-5 mins",
        "availablePickupTimes": null,
        "isPaused": false,
        "id": 4776,
        "title": "Example Title"
    },
    {
        "description": "Example Title",
        "section": "",
        "imageUrl": "https://storage.tapin2.co/images/example.jpg",
        "imageUrlMobile": "",
        "imageUrlTerminal": "Example Venue",
        "imageUrlPreorder": "",
        "imageUrlMenuPortrait": "",
        "imageUrlMenuLandscape": "",
        "orderingEnabled": true,
        "isActive": false,
        "pauseExpiration": "05/17/2026 8:54 AM",
        "isHawker": false,
        "orderId": 8,
        "isDelivery": false,
        "isPickup": true,
        "waitTime": "approx wait 0-5 mins",
        "availablePickupTimes": null,
        "isPaused": false,
        "id": 2001,
        "title": "Example Title"
    }
]
```

## Venue-Specific Notes

- **Sandbox Status**: Active and functional.
- **Payload Size**: The live sandbox returns a valid data payload.

---
[🔗 View Original Documentation](https://api.tapin2.co/Help/Api/GET-v2-venues-venueId-locations-includePreorder)

[← Back to Endpoint Registry](../README.md)
