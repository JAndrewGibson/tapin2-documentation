# Venue Model

The `Venue` object contains top-level configuration and metadata for a physical location.

| Field | Type | Description |
| :--- | :--- | :--- |
| `id` | Integer | Unique identifier for the venue. |
| `title` | String | Full name of the venue. |
| `displayName` | String | Public-facing display name. |
| `taxRate` | Float | Tax percentage applied to sales. |
| `isCashless` | Boolean | Whether the venue is cashless. |
| `timeZoneInfo` | Object | Timezone metadata used for timestamp localization. |
| `fees` | Array | List of service fees and administrative charges. |

## Example JSON
```json
{
    "id": 5843,
    "title": "Example Venue",
    "displayName": "Example Venue",
    "taxRate": 7.75,
    "isCashless": true
}
```
