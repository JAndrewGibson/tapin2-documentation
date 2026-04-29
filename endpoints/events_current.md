# Current Event

Retrieve the currently active event for a venue. This is used to determine which products to display and which price levels to apply.

- **Endpoint**: `v2/venues/{venueId}/events/current`
- **Method**: `GET`
- **Authentication**: Required (`Key` header)

## Parameters

| Name | Type | Located In | Description |
| :--- | :--- | :--- | :--- |
| `venueId` | Integer | Path | The unique identifier for the venue. |

## Response Structure

Returns an event object if an event is currently active, or `null` if no event is scheduled for the current time.

| Field | Type | Description |
| :--- | :--- | :--- |
| `id` | Integer | Unique identifier for the event. |
| `title` | String | Name of the event (e.g., "Game Day"). |
| `startDate` | String | Scheduled start time of the event. |
| `orderingStartDate` | String | Time when ordering is enabled for the event. |
| `endDate` | String | Scheduled end time of the event. |
| `eventType` | Object | Metadata about the event category. |

### Event Type Object

| Field | Type | Description |
| :--- | :--- | :--- |
| `id` | Integer | ID of the event type. |
| `title` | String | Category name (e.g., "Standard Game", "Concert"). |
| `priceLevelId` | Integer | The price level mapping used for products during this event. |

## Example Response (Sanitized)

```json
{
    "id": 99999,
    "title": "Example Event",
    "startDate": "04/29/2026 5:00 PM",
    "orderingStartDate": "04/29/2026 3:30 PM",
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

- **Suite-based Venues**: May return `null` more frequently if events are restricted to specific preorder windows.
- **Concessions-based Venues**: Generally returns the active game or concert currently in progress.

---
[← Back to Endpoint Registry](../README.md)
