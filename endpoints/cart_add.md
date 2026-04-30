# Add to Cart

Add a product to the user's shopping cart.

- **Endpoint**: `v2/cart/add`
- **Method**: `POST`
- **Authentication**: Required (`Key` header)

> [!CAUTION]
> **Status: ❌ Blocked (500 Error)**
> This endpoint is currently non-functional in the sandbox environment. It consistently returns a `500 Internal Server Error` during the `OrderingCutOff` validation phase.

## Expected Request Body

| Field | Type | Description |
| :---| :---| :---|
| `venueId` | Integer | **Required**. Unique identifier for the venue. |
| `locationId` | Integer | **Required**. Service location for the order. |
| `eventId` | Integer | **Required**. Active event ID. |
| `productId` | Integer | **Required**. ID of the product to add. |
| `quantity` | Integer | Number of units to add. |
| `priceLevelId` | Integer | (Optional) Specific price level to apply. |

## Verification Log (Attempts)

The following variations were tested at **Venue B** (Concessions) using active event `EVENT_ID_1` and valid location/product combinations:

| Attempt | Payload Strategy | Result | Note |
| :---| :---| :---| :---|
| 1 | `{"venueId", "locationId", "productId", "quantity"}` | `500` | Missing `eventId` (KeyNotFoundException) |
| 2 | Including `eventId` | `500` | ArgumentNullException in `OrderingCutOff` |
| 3 | Including `items` array | `500` | Same `OrderingCutOff` failure |
| 4 | PascalCase keys | `500` | Same `OrderingCutOff` failure |
| 5 | Including `DeviceId` | `500` | Same `OrderingCutOff` failure |

### Probing Conclusions
Despite providing valid `eventId` and `locationId` contexts (verified against successful orders in the same environment), the backend logic for ordering cut-off validation appears to encounter a null reference when processing these requests. This suggests either a missing required session-level field or a backend misconfiguration in the sandbox environment.

---
[🔗 View Original Documentation](https://api.tapin2.co/Help/Api/POST-v2-cart-add)

[← Back to Endpoint Registry](../README.md)
