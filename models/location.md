# Location Model

The `Location` object represents a specific point of sale or service area (e.g., Stand, Bar, Suite) within a venue.

| Field | Type | Description |
| :--- | :--- | :--- |
| `id` | Integer | Unique identifier for the location. |
| `title` | String | Name of the location. |
| `type` | Integer | Location type code. |
| `isAvailable` | Boolean | Whether the location is currently open/available. |
| `posRefId` | String | Reference ID for POS systems. |

## Example JSON
```json
{
    "id": 11829,
    "title": "Section 258 Bar",
    "type": 2,
    "isAvailable": true
}
```
