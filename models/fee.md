# Fee Model

The `Fee` object represents a service charge or administrative fee applied to an order.

| Field | Type | Description |
| :--- | :--- | :--- |
| `id` | Integer | Unique identifier for the fee. |
| `title` | String | Name of the fee (e.g., "Admin Fee"). |
| `amount` | Float | The numerical value of the fee. |
| `isPercentage` | Boolean | Whether the amount is a percentage or a flat fee. |
| `isActive` | Boolean | Whether the fee is currently active. |

## Example JSON
```json
{
    "id": 1,
    "title": "Service Fee",
    "amount": 13.0,
    "isPercentage": true,
    "isActive": true
}
```
