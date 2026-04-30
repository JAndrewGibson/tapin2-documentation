# Venue Translations

Retrieve localization and translation strings for the venue's user interface.

- **Endpoint**: `v2/venues/{venueId}/translations`
- **Method**: `GET`
- **Authentication**: Required (`Key` header)

## Parameters

| Name | Type | Located In | Description |
| :---| :---| :---| :---|
| `venueId` | Integer | Path | The unique identifier for the venue. |

## Response Structure

Returns a JSON object mapping translation keys to localized strings. 

*Note: Many venues may return an empty object if no custom translations are configured.*

## Example Response (Sanitized)

```json
{}
```

## Venue-Specific Notes

- **Empty Responses**: As of current testing, both Suite-based and Concessions-based test venues returned empty translation objects. This suggests that translations may be handled at a global or application level rather than per-venue, or are simply not used in these specific environments.

---
[🔗 View Original Documentation](https://api.tapin2.co/Help/Api/GET-v2-venues-venueId-translations)

[← Back to Endpoint Registry](../README.md)
