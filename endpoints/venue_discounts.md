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
| `code` | String | The code used to trigger the discount (e.g., promo code or employee ID). |
| `amount` | Float | The value of the discount. |
| `isPercentage` | Boolean | Whether the amount is a percentage (e.g., 1.0 = 100%) or a flat value. |
| `isActive` | Boolean | Whether the discount is currently available for use. |
| `isProductSpecific`| Boolean | If true, the discount only applies to products listed in `productIds`. |
| `productIds` | Array | List of product IDs eligible for this discount. |
| `maxUseCount` | Integer | Limit on how many times this specific code can be used. |

## Example Response (Sanitized)

```json
[
    {
        "id": 1001,
        "title": "Example Manager Discount",
        "code": "EMP123",
        "amount": 1.0,
        "isPercentage": true,
        "isActive": true,
        "isProductSpecific": false,
        "productIds": []
    },
    {
        "id": 1002,
        "title": "$5 Off Promotion",
        "code": "SAVE5",
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
[← Back to Endpoint Registry](README.md)
