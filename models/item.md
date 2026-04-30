# Item Model

The `Item` object represents a specific product instance within an order.

| Field | Type | Description |
| :--- | :--- | :--- |
| `id` | Integer | Unique identifier for the line item. |
| `status` | Integer | Status of the item (e.g., `2` for fulfilled). |
| `locationId` | Integer | The ID of the location where the item is prepared. |
| `productId` | Integer | The ID of the associated product. |
| `quantity` | Integer | Number of units ordered. |
| `pricePer` | Float | Price per unit. |
| `modifiers` | Array | List of modifiers applied to this item. |

## Example JSON
```json
{
    "id": 94257760,
    "status": 2,
    "locationId": 11829,
    "productId": 298098,
    "quantity": 1,
    "pricePer": 9.0,
    "modifiers": []
}
```
