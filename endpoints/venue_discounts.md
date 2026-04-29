# Venue Discounts

Retrieve all promotional discounts and manager overrides configured for a venue.

- **Endpoint**: `v2/venues/{venueId}/discounts`
- **Method**: `GET`
- **Authentication**: Required (`Key` header)

## Parameters

| Name | Type | Located In | Description |
| :--- | :--- | :--- | :--- |
| `venueId` | Integer | Path | The unique identifier for the venue. |

## Response Structure

Returns an array of discount objects.

| Field | Type | Description |
| :--- | :--- | :--- |
| `id` | Integer | Unique identifier for the discount. |
| `title` | String | Public name of the discount. |
| `code` | String | The alphanumeric promo code (if applicable). |
| `description` | String | Detailed description of the discount rules. |
| `amount` | Float | The value of the discount. |
| `amountString`| String | Human-readable value (e.g., "10%", "$5.00"). |
| `isPercentage` | Boolean | Whether the amount is a percentage or flat value. |
| `isActive` | Boolean | Whether the discount is currently enabled. |
| `autoApply` | Boolean | Whether the discount is applied automatically if criteria are met. |
| `isProductSpecific`| Boolean | Whether the discount only applies to certain products. |
| `productIds` | Array | List of product IDs eligible for the discount. |
| `minSubtotal` | Float | Minimum cart subtotal required to use the discount. |
| `maxUseCount` | Integer | Limit on how many times this specific code can be used. |

## Example Response (Sanitized)

```json
[
    {
        "id": 8001,
        "title": "EXAMPLE_DISCOUNT",
        "code": "PROMO2026",
        "description": "Seasonal fan discount",
        "amount": 5.0,
        "isPercentage": false,
        "isActive": true,
        "isProductSpecific": true,
        "productIds": [2001, 2002, 2003]
    }
]
```

## Venue-Specific Notes

- **Discounts vs Manager Pins**: Many "discounts" in the system actually represent manager overrides (100% off) used for specific internal workflows.
- **Product Specificity**: Some discounts are restricted to specific items (e.g., "Buy a burger, get a discount"). These will have `isProductSpecific: true`.

---
[← Back to Endpoint Registry](../README.md)
