# Remove from Cart

Remove an item from the user's shopping cart.

- **Endpoint**: `v2/cart/remove`
- **Method**: `POST`
- **Authentication**: Required (`Key` header)

> [!CAUTION]
> **Status: ❌ Blocked (500 Error)**
> This endpoint is currently assumed to be non-functional in the sandbox environment, as it shares the same base controller logic as the `add` endpoint which consistently fails with a 500 error.

## Expected Request Body

| Field | Type | Description |
| :--- | :--- | :--- |
| `venueId` | Integer | **Required**. Unique identifier for the venue. |
| `locationId` | Integer | **Required**. Service location for the order. |
| `cartItemId` | Integer | **Required**. The unique ID of the line item in the cart. |

---
[← Back to Endpoint Registry](../README.md)
