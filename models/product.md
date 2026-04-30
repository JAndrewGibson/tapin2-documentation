# Product Model

The `Product` object represents a sellable item within a venue.

| Field | Type | Description |
| :--- | :--- | :--- |
| `id` | Integer | Unique identifier for the product. |
| `title` | String | Name of the product. |
| `description` | String | Long-form description. |
| `price` | Float | Base price of the product. |
| `imageUrl` | String | URL to the product image. |
| `categoryId` | Integer | ID of the primary category. |
| `posRefId` | String | Reference ID for POS systems. |
| `isAvailable` | Boolean | Whether the product is currently in stock. |
| `modifiers` | Array | List of available modifier groups for this product. |

## Example JSON
```json
{
    "id": 298050,
    "title": "BREWERY X QUACK IPA 19.2OZ CAN",
    "price": 17.0,
    "categoryId": 6697,
    "isAvailable": true
}
```
