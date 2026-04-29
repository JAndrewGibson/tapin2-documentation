# Venue Details

Get detailed information about a specific venue, including tax rates, tip options, and service fees.

- **Endpoint**: `v2/venues/{venueId}/details`
- **Method**: `GET`
- **Authentication**: Required (`Key` header)

## Parameters

| Name | Type | Located In | Description |
| :--- | :--- | :--- | :--- |
| `venueId` | Integer | Path | The unique identifier for the venue (e.g., Suite-based or Concessions-based ID). |

## Response Structure

The response is a JSON object containing venue configuration and metadata.

| Field | Type | Description |
| :--- | :--- | :--- |
| `id` | Integer | The unique ID of the venue. |
| `title` | String | The full name of the venue. |
| `displayName` | String | The name used for public display. |
| `coords` | Object | Latitude and longitude coordinates. |
| `taxRate` | Float | The primary tax rate for the venue (e.g., 7.75). |
| `tipOptions` | Array | Suggested tip percentages (e.g., [18, 20, 22]). |
| `fees` | Array | List of service fees and administrative charges. |
| `timeZoneInfo` | Object | Detailed timezone data including daylight savings rules. |
| `suiteUiOptions` | Integer | Bitmask for suite-specific UI configurations. |
| `preorderUiOptions`| Integer | Bitmask for preorder-specific UI configurations. |

### Fee Object Schema

| Field | Type | Description |
| :--- | :--- | :--- |
| `id` | Integer | Unique identifier for the fee. |
| `title` | String | Name of the fee (e.g., "Admin Fee", "Service Charge"). |
| `amount` | Float | The numerical value of the fee. |
| `isPercentage` | Boolean | Whether the amount is a percentage or a flat fee. |
| `isActive` | Boolean | Whether the fee is currently being applied. |
| `services` | Array | IDs of services this fee applies to. |

## Example Response (Suite-based Venue)

```json
{
    "id": 1234,
    "title": "Example Venue - Suites",
    "displayName": "Example Venue",
    "coords": {
        "lat": 0.000,
        "lng": 0.000
    },
    "taxRate": 7.75,
    "tipOptions": [18, 20, 22],
    "fees": [
        {
            "id": 1,
            "title": "Service Fee",
            "amount": 13.0,
            "isPercentage": true,
            "isActive": true,
            "services": [1, 2, 3]
        }
    ],
    "suiteUiOptions": 25088
}
```

## Venue-Specific Notes

- **Suite-based Venues**: Typically includes higher `suiteUiOptions` and multiple administrative fees specific to suite service.
- **Concessions-based Venues**: Often includes more complex `fees` structures with `offLocationIds` for specific location exclusions.

---
[← Back to Endpoint Registry](../README.md)
