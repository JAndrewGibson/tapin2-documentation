# Create Category

Create a new product category. This endpoint is typically used to synchronize categories with external systems or for manual menu management.

- **Endpoint**: `{version}/Category`
- **Method**: `POST`
- **Authentication**: Required (`Key` header)

## Request Body

The request body must be a JSON object containing the category details.

| Field | Type | Description |
| :--- | :--- | :--- |
| `venueId` | Integer | **Required**. The unique identifier for the venue. |
| `title` | String | **Required**. The name of the category (e.g., "TEST CATEGORY"). |
| `isActive` | Boolean | Whether the category is enabled for display. |
| `orderId` | Integer | The display order for the UI. |
| `posRefId` | String | External reference ID for POS integration. |
| `locationIds` | Array | List of location IDs where this category should be available. |
| `subcategories` | Array | List of nested subcategories (optional). |

## Status: ❌ Blocked

This endpoint is currently non-functional in the sandbox environment. All attempts to create a category result in a `500 Internal Server Error`.

### Known Deficiency

The error occurs during the `SubmitIntegrationsAsync` phase of the request, suggesting a failure in the POS synchronization middleware.

```json
{
  "message": "An error has occurred.",
  "exceptionMessage": "Object reference not set to an instance of an object.",
  "exceptionType": "System.NullReferenceException",
  "stackTrace": "   at Tap.Web.Api.Controllers.BaseController.SubmitIntegrationsAsync..."
}
```

## Verification Log (Attempts)

The following payload variations were tested against `v2/Category` for **Venue A** (Suites) and **Venue B** (Concessions):

| Attempt | Payload Strategy | Result | Note |
| :--- | :--- | :--- | :--- |
| 1 | `{"venueId": VENUE_ID_A, "title": "TEST", "isActive": true}` | `500` | Standard camelCase minimal |
| 2 | `{"VenueId": VENUE_ID_A, "Title": "TEST", "IsActive": true}` | `500` | PascalCase minimal |
| 3 | Full object with `ImageUrl`, `OrderId`, `PosRefId`, etc. | `500` | Matching GET response structure |
| 4 | Including `LocationId`: `LOC_ID_1` | `500` | Attempting to provide location context |
| 5 | Including `EventId`: `EVENT_ID_1` | `500` | Attempting to provide event context |
| 6 | Wrapped object: `{"Category": {...}}` | `401` | Required fields not at top level |
| 7 | Array of objects: `[{...}]` | `401` | Endpoint does not accept bulk POST |

### Probing Conclusions
- **Auth Trigger**: The API requires `venueId` at the top level of the JSON body. If missing, it returns `401 Unauthorized`.
- **Backend Crash**: Once `venueId` is provided, the API proceeds to integration logic where it consistently crashes with a `NullReferenceException`.

---
[← Back to Endpoint Registry](../README.md)
