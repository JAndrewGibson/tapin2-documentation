# Venue Content

Retrieve CMS-driven content and UI duration settings for a specific location within a venue.

- **Endpoint**: `v2/venues/{venueId}/content`
- **Method**: `GET`
- **Authentication**: Required (`Key` header)

## Parameters

| Name | Type | Located In | Description |
| :--- | :--- | :--- | :--- |
| `venueId` | Integer | Path | The unique identifier for the venue. |
| `locationId` | Integer | Query | The unique identifier for the location (e.g., a specific suite or stand). |

## Response Structure

Returns an object containing metadata and content configuration.

| Field | Type | Description |
| :--- | :--- | :--- |
| `venueId` | Integer | The ID of the venue. |
| `locationId` | Integer | The ID of the location. |
| `idleTimeUntilWarning` | Integer | Time (in seconds) before an idle warning is shown on terminal/kiosk. |
| `orderConfirmationDuration` | Integer | How long the confirmation screen stays visible. |
| `timeoutWarningDuration` | Integer | Duration of the timeout warning countdown. |
| `content` | Object | Dictionary of CMS-managed content blocks (e.g., promotional text, banners). |

## Example Response (Sanitized)

```json
{
    "venueId": 123,
    "locationId": 456,
    "idleTimeUntilWarning": 60,
    "orderConfirmationDuration": 10,
    "timeoutWarningDuration": 15,
    "content": {}
}
```

## Venue-Specific Notes

- **Empty Content**: Like translations, the `content` dictionary is frequently empty unless specific overrides have been configured in the Tapin2 management dashboard.

---
[← Back to Endpoint Registry](README.md)
