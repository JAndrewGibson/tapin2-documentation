# Search Events (Range)

Search for events within a specific date range for a venue. This endpoint provides the same data as the GET [Events Range](events_range.md) endpoint but uses a POST method with the venue identifier in the request body.

- **Endpoint**: `v2/events/{minDate}/{maxDate}`
- **Method**: `POST`
- **Authentication**: Required (`Key` header)

## Parameters

| Name | Type | Located In | Description |
| :--- | :--- | :--- | :--- |
| `minDate` | String | Path | Start of the date range (`YYYY-MM-DD`). |
| `maxDate` | String | Path | End of the date range (`YYYY-MM-DD`). |

## Request Body

| Field | Type | Description |
| :--- | :--- | :--- |
| `venueId` | Integer | **Required**. The unique identifier for the venue. |

## Response Structure

Returns an array of event objects.

| Field | Type | Description |
| :--- | :--- | :--- |
| `id` | Integer | Unique identifier for the event. |
| `title` | String | Public name of the event. |
| `startDate` | String | Scheduled start time (format: `MM/DD/YYYY H:MM AM/PM`). |
| `endDate` | String | Scheduled end time. |
| `orderingStartDate`| String | When customers can begin placing orders. |
| `lastCallDate` | String | When ordering will be disabled. |
| `isLastCall` | Boolean | Whether the event is currently in the "Last Call" period. |
| `isCurrent` | Boolean | Whether this is the active/live event at the venue. |
| `taxExempt` | Boolean | Whether sales for this event are tax-exempt. |
| `includeInReports` | Boolean | Whether data from this event is included in standard reports. |
| `address` | String | Physical address or location name of the event. |
| `eventType` | Object | Category/Pricing configuration for the event. |

## Example Response (Sanitized)

```json
[
    {
        "id": 1001,
        "title": "EXAMPLE_EVENT_A",
        "startDate": "04/25/2026 2:00 AM",
        "orderingStartDate": "04/25/2026 12:00 AM",
        "endDate": "04/25/2026 11:00 AM",
        "taxExempt": false,
        "includeInReports": true,
        "address": "123 Event Way",
        "lastCallDate": null,
        "isLastCall": true,
        "isCurrent": false,
        "eventType": {
            "id": 50,
            "title": "Example Event Type",
            "priceLevelId": null,
            "customPaymentId": null,
            "imageUrl": ""
        }
    }
]
```

## Implementation Notes

- **Authorization**: This endpoint requires `venueId` to be passed in the request body. If the body is empty or missing the `venueId` key, the API returns a `500 Internal Server Error` with a `KeyNotFoundException`.
- **Parity**: The response data structure is identical to the GET version at `v2/venues/{venueId}/events/{minDate}/{maxDate}`.

---
[← Back to Endpoint Registry](../README.md)
