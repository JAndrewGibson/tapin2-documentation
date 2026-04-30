# Discount Model

The `Discount` object represents a reduction in the order total, typically from a coupon or manager override.

| Field | Type | Description |
| :--- | :--- | :--- |
| `id` | Integer | Unique identifier for the discount. |
| `title` | String | Name of the discount. |
| `code` | String | The code used to apply the discount. |
| `amount` | Float | The total amount deducted from the order. |

## Example JSON
```json
{
    "id": 507,
    "title": "Manager Discount",
    "code": "050709128",
    "amount": 9.0
}
```
