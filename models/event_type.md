# EventType Model

The `EventType` object defines the pricing level and categorical grouping for an event.

| Field | Type | Description |
| :--- | :--- | :--- |
| `id` | Integer | Unique identifier for the event type. |
| `title` | String | Human-readable name (e.g., "Standard", "Post-Season"). |
| `priceLevelId` | Integer | The ID of the price level associated with this event type. |
| `customPaymentId` | Integer | (Optional) ID for custom payment handling. |
| `imageUrl` | String | (Optional) URL to an icon representing the event type. |

## Example JSON
```json
{
    "id": 40,
    "title": "DUCKS",
    "priceLevelId": 23,
    "customPaymentId": null,
    "imageUrl": ""
}
```
