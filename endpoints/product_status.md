# Product Status

Check the current availability status of a specific product.

- **Endpoint**: `v2/venues/{venueId}/products/{productId}/status`
- **Method**: `GET`
- **Authentication**: Required (`Key` header)

## Parameters

| Name | Type | Located In | Description |
| :--- | :--- | :--- | :--- |
| `venueId` | Integer | Path | The unique identifier for the venue. |
| `productId` | Integer | Path | The unique identifier for the product. |

## Response Structure

Returns a Boolean value.

| Value | Description |
| :--- | :--- |
| `true` | The product is active and available for ordering. |
| `false` | The product is inactive or sold out. |

## Example Response

```json
true
```

## Venue-Specific Notes

- **Real-time Availability**: This is a lightweight alternative to fetching the full inventory or product list when only a single item's status is needed.

---
[← Back to Endpoint Registry](../README.md)
