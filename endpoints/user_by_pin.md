# User by PIN

Retrieve user profile and permission data by providing a unique PIN.

- **Endpoint**: `v4/venues/{venueId}/users/pin/{pin}`
- **Method**: `GET`
- **Authentication**: Required (`Key` header)

## Parameters

| Name | Type | Located In | Description |
| :--- | :--- | :--- | :--- |
| `venueId` | Integer | Path | The unique identifier for the venue. |
| `pin` | String | Path | The unique alphanumeric or numeric PIN for the user. |

## Response Structure

Returns a user profile object.

| Field | Type | Description |
| :--- | :--- | :--- |
| `id` | Integer | Unique identifier for the user. |
| `name` | String | Display name of the user. |
| `locationId` | Integer | (Optional) The specific location the user is assigned to. |
| `locationGroupId` | Integer | (Optional) The group of locations the user is assigned to. |
| `deviceId` | String | (Optional) The specific device ID the user is logged into. |
| `isManager` | Boolean | Whether the user has administrative/managerial permissions. |
| `isHawker` | Boolean | Whether the user is designated as a mobile hawker. |
| `isServer` | Boolean | Whether the user is a table/suite server. |
| `isRunner` | Boolean | Whether the user is an order runner. |
| `isKdsOperator` | Boolean | Whether the user is authorized to operate the Kitchen Display System. |

## Example Response (Sanitized)

```json
{
    "id": 123456,
    "name": "Example User",
    "locationId": null,
    "locationGroupId": null,
    "deviceId": null,
    "isHawker": false,
    "isServer": true,
    "isRunner": false,
    "isManager": false,
    "isKdsOperator": true
}
```

## Venue-Specific Notes

- **Permission Checks**: This endpoint is frequently used by handheld terminals and kiosks to authenticate staff and determine which UI modules (Manager Dashboard, KDS, etc.) should be enabled.
- **PIN Security**: PINs are typically 4-9 digits long and are managed within the Tapin2 Management Console.

---
[← Back to Endpoint Registry](../README.md)
