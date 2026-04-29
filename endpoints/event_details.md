# Event Details

Retrieve detailed metadata for a specific event by its ID.

- **Endpoint**: `v2/venues/{venueId}/events/{eventId}`
- **Method**: `GET`
- **Authentication**: Required (`Key` header)

## Parameters

| Name | Type | Located In | Description |
| :--- | :--- | :--- | :--- |
| `venueId` | Integer | Path | The unique identifier for the venue. |
| `eventId` | Integer | Path | The unique identifier for the event. |

## Response Structure

Returns a single event object. The structure is identical to the [Current Event](events_current.md) endpoint.

| Field | Type | Description |
| :--- | :--- | :--- |
| `id` | Integer | Unique identifier for the event. |
| `title` | String | Name of the event. |
| `startDate` | String | Scheduled start time. |
| `eventType` | Object | Metadata about the event category. |

## Example Response (Sanitized)

```json
{
    "id": 99999,
    "title": "Example Event",
    "startDate": "04/29/2026 5:00 PM",
    "endDate": "04/30/2026 12:30 AM",
    "isCurrent": true,
    "eventType": {
        "id": 10,
        "title": "EXAMPLE_CATEGORY",
        "priceLevelId": 23
    }
}
```

## Venue-Specific Notes

- **Price Levels**: The `priceLevelId` within the `eventType` object is critical for correctly calculating product prices for this specific event.
- **Reporting**: The `includeInReports` field indicates if orders from this event should be included in financial exports.

---
[← Back to Endpoint Registry](../README.md)
