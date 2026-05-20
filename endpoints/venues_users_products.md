# GET v2/venues/{venueId}/users/products

Retrieve details for the specified endpoint.

- **Endpoint**: `v2/venues/{venueId}/users/products`
- **Method**: `GET`
- **Authentication**: Required (`Key` header)

## Parameters

| Name | Type | Located In | Description |
| :---| :---| :---| :---|
| `venueId` | Integer | Path | The parameter in path. |


## Response Structure

| Field | Type | Description |
| :---| :---| :---|
| `[].venueId` | Integer | Unique identifier for the venue. |
| `[].locationId` | Null | Unique identifier for the location. |
| `[].usrId` | Integer | Unique identifier for the usr. |
| `[].name` | String | The name or title of the name. |
| `[].pin` | String |  |
| `[].isHawker` | Boolean |  |
| `[].isServer` | Boolean |  |
| `[].isRunner` | Boolean |  |
| `[].isManager` | Boolean |  |
| `[].isKdsOperator` | Boolean |  |
| `[].isCashier` | Boolean |  |
| `[].expiresAt` | Integer |  |
| `[].products` | Array |  |

## Example Response (Sanitized)

```json
[
    {
        "venueId": 1001,
        "locationId": null,
        "usrId": 5411,
        "name": "John Doe",
        "pin": "",
        "isHawker": false,
        "isServer": false,
        "isRunner": false,
        "isManager": false,
        "isKdsOperator": true,
        "isCashier": false,
        "expiresAt": 1780508924,
        "products": []
    },
    {
        "venueId": 1001,
        "locationId": null,
        "usrId": 536792,
        "name": "John Doe",
        "pin": "7070",
        "isHawker": false,
        "isServer": false,
        "isRunner": false,
        "isManager": true,
        "isKdsOperator": false,
        "isCashier": false,
        "expiresAt": 1780508924,
        "products": []
    }
]
```

## Venue-Specific Notes

- **Sandbox Status**: Active and functional.
- **Payload Size**: The live sandbox returns a valid data payload.

---
[🔗 View Original Documentation](https://api.tapin2.co/Help/Api/GET-v2-venues-venueId-users-products)

[← Back to Endpoint Registry](../README.md)
