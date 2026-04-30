# Order Item Bump

Mark an order item as fulfilled or progress it through the Kitchen Display System (KDS) workflow.

- **Endpoint**: `v4/venues/{venueId}/orders/{orderId}/items/{itemId}/bump`
- **Method**: `POST`
- **Authentication**: Required (`Key` header)

## Parameters

| Name | Type | Located In | Description |
| :--- | :--- | :--- | :--- |
| `venueId` | Integer | Path | The unique identifier for the venue. |
| `orderId` | Integer | Path | The unique identifier for the order. |
| `itemId` | Integer | Path | The unique identifier for the specific line item within the order. |

## Request Body

This endpoint does not require a request body. Send an empty JSON object `{}`.

## Response Structure

Returns a boolean indicating success.

```json
true
```

## Implementation Notes

- **KDS Integration**: This endpoint is primarily used by fulfillment screens to "bump" (remove) items from the pending display once they have been prepared or handed to the customer.
- **State Change**: Bumping an item typically updates its internal status and records a fulfillment timestamp (returned as `prepDate` or `outDate` in standard order responses).
- **Idempotency**: Repeatedly bumping the same item will continue to return `true` as long as the order and item IDs are valid.

---
[← Back to Endpoint Registry](../README.md)
