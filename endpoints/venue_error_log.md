# Error Logging

Report client-side errors, stack traces, and application state to the Tapin2 logging system. This endpoint is typically used by mobile apps, kiosks, and terminals to provide telemetry to venue administrators.

- **Endpoint**: `v2/venues/{venueId}/error`
- **Method**: `POST`
- **Authentication**: Required (`Key` header)

## Parameters

| Name | Type | Located In | Description |
| :---| :---| :---| :---|
| `venueId` | Integer | Path | The unique identifier for the venue. |

## Request Body

| Field | Type | Description |
| :---| :---| :---|
| `message` | String | **Required**. The error message or description. |
| `stackTrace` | String | The technical stack trace or error details. |
| `deviceId` | String | The identifier of the device reporting the error. |
| `appVersion` | String | The version of the application reporting the error. |
| `userId` | Integer | (Optional) The ID of the user logged in when the error occurred. |

## Response Structure

Returns `204 No Content` on success.

## Implementation Notes

- **Telemetry**: Errors reported here are typically visible in the Tapin2 Management Console under the "Logs" or "Device Health" sections.
- **Payload Size**: Keep stack traces concise to avoid hitting request size limits.

---
[🔗 View Original Documentation](https://api.tapin2.co/Help/Api/POST-v2-venues-venueId-error)

[← Back to Endpoint Registry](../README.md)
