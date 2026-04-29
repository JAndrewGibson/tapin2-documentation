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
| `{slug}` | Object | A content entry identified by a unique slug or numeric ID. |
| `{slug}.{locale}` | String | The localized content string or HTML snippet. |
| `idleTimeUntilWarning` | Integer | Time (in seconds) before an idle warning is shown on terminal/kiosk. |
| `orderConfirmationDuration` | Integer | How long the confirmation screen stays visible. |
| `timeoutWarningDuration` | Integer | Duration of the timeout warning countdown. |
| `content` | Object | Dictionary of CMS-managed content blocks (e.g., promotional text, banners). |

## Example Response (Sanitized)

```json
{
    "mobileIdleNoEvent": {
        "en-US": "<h1>EVENT ENDED</h1><p>Ordering for this event has ended.</p>"
    },
    "mobilePaymentHeader": {
        "en-US": "<h1>Final Step</h1><p>Please select a payment method.</p>"
    },
    "suiteFeeLabel": {
        "en-US": "Service Charge"
    }
}
```

## Venue-Specific Notes

- **Empty Content**: Like translations, the `content` dictionary is frequently empty unless specific overrides have been configured in the Tapin2 management dashboard.

---
[← Back to Endpoint Registry](../README.md)
