# GET v4/venues/{venueId}/locations/{locationId}/products/small/modified/{fromDate}/{toDate}

Retrieve details for the specified endpoint.

- **Endpoint**: `v4/venues/{venueId}/locations/{locationId}/products/small/modified/{fromDate}/{toDate}`
- **Method**: `GET`
- **Authentication**: Required (`Key` header)

## Parameters

| Name | Type | Located In | Description |
| :---| :---| :---| :---|
| `venueId` | Integer | Path | The parameter in path. |
| `locationId` | Integer | Path | The parameter in path. |
| `fromDate` | String | Path | The parameter in path. |
| `toDate` | String | Path | The parameter in path. |


## Response Structure

| Field | Type | Description |
| :---| :---| :---|
| `[].id` | Integer | Unique identifier for the record. |
| `[].title` | String | The name or title of the title. |
| `[].fgId` | Integer | Unique identifier for the fg. |
| `[].price` | Float | The price or financial value of the item. |
| `[].eventPrice` | Float | The price or financial value of the item. |
| `[].modifyDate` | String | Timestamp in standard formatting. |
| `[].isActive` | Boolean | Indicates whether the record is currently active. |
| `[].upc` | String |  |
| `[].modGroups` | Array |  |

## Example Response (Sanitized)

```json
[
    {
        "id": 50001,
        "title": "Example Title",
        "fgId": 523,
        "price": 12.0,
        "eventPrice": 12.0,
        "modifyDate": "04/23/2026 11:07 PM",
        "isActive": true,
        "upc": "",
        "modGroups": []
    },
    {
        "id": 339692,
        "title": "Example Title",
        "fgId": 523,
        "price": 9.0,
        "eventPrice": 9.0,
        "modifyDate": "05/07/2026 5:45 PM",
        "isActive": true,
        "upc": "",
        "modGroups": []
    }
]
```

## Venue-Specific Notes

- **Sandbox Status**: Active and functional.
- **Payload Size**: The live sandbox returns a valid data payload.

---
[🔗 View Original Documentation](https://api.tapin2.co/Help/Api/GET-v4-venues-venueId-locations-locationId-products-small-modified-fromDate-toDate)

[← Back to Endpoint Registry](../README.md)
