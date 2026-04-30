# Modifier Model

The `Modifier` object represents an adjustment or option selected for a specific item in an order.

| Field | Type | Description |
| :--- | :--- | :--- |
| `id` | Integer | Unique identifier for the modifier. |
| `title` | String | Display name of the modifier. |
| `priceDiff` | Float | The price adjustment applied by this modifier. |
| `quantity` | Integer | Quantity of the modifier applied. |

## Example JSON
```json
{
    "id": 1833730,
    "title": "MICHELADA UPGRADE",
    "priceDiff": 7.0,
    "quantity": 1
}
```
