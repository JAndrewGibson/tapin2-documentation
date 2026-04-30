# Venue Details

Get detailed information about a specific venue, including tax rates, tip options, and service fees.

- **Endpoint**: `v2/venues/{venueId}/details`
- **Method**: `GET`
- **Authentication**: Required (`Key` header)

## Parameters

| Name | Type | Located In | Description |
| :
## Related Endpoints

- [Venue Locations](venue_locations.md)
- [Venue Discounts](venue_discounts.md)

--- | :
## Related Endpoints

- [Venue Locations](venue_locations.md)
- [Venue Discounts](venue_discounts.md)

--- | :
## Related Endpoints

- [Venue Locations](venue_locations.md)
- [Venue Discounts](venue_discounts.md)

--- | :
## Related Endpoints

- [Venue Locations](venue_locations.md)
- [Venue Discounts](venue_discounts.md)

--- |
| `venueId` | Integer | Path | The unique identifier for the venue (e.g., Suite-based or Concessions-based ID). |

## Response Structure

The response is a JSON object containing venue configuration and metadata.

| Field | Type | Description |
| :
## Related Endpoints

- [Venue Locations](venue_locations.md)
- [Venue Discounts](venue_discounts.md)

--- | :
## Related Endpoints

- [Venue Locations](venue_locations.md)
- [Venue Discounts](venue_discounts.md)

--- | :
## Related Endpoints

- [Venue Locations](venue_locations.md)
- [Venue Discounts](venue_discounts.md)

--- |
| `id` | Integer | The unique ID of the venue. |
| `title` | String | The full name of the venue. |
| `displayName` | String | The name used for public display. |
| `logoUrl` | String | URL to the venue's primary logo. |
| `receiptLogoUrl` | String | URL to the logo used on printed receipts. |
| `coords` | Object | Latitude and longitude coordinates. |
| `taxRate` | Float | The primary tax rate for the venue (e.g., 7.75). |
| `tipOptions` | Array | Suggested tip percentages (e.g., [18, 20, 22]). |
| `isCashless` | Boolean | Whether the venue only accepts non-cash payments. |
| `isAlcoholService` | Boolean | Whether the venue is configured for alcohol service. |
| `fees` | [Array](../models/fee.md) | List of service fees and administrative charges. |
| `timeZoneInfo` | Object | Detailed timezone data including daylight savings rules. |
| `suiteUiOptions` | Integer | Bitmask for suite-specific UI configurations. |
| `preorderUiOptions`| Integer | Bitmask for preorder-specific UI configurations. |

### Fee Object Schema

| Field | Type | Description |
| :
## Related Endpoints

- [Venue Locations](venue_locations.md)
- [Venue Discounts](venue_discounts.md)

--- | :
## Related Endpoints

- [Venue Locations](venue_locations.md)
- [Venue Discounts](venue_discounts.md)

--- | :
## Related Endpoints

- [Venue Locations](venue_locations.md)
- [Venue Discounts](venue_discounts.md)

--- |
| `id` | Integer | Unique identifier for the fee. |
| `title` | String | Name of the fee (e.g., "Admin Fee", "Service Charge"). |
| `amount` | Float | The numerical value of the fee. |
| `isPercentage` | Boolean | Whether the amount is a percentage or a flat fee. |
| `isActive` | Boolean | Whether the fee is currently being applied. |
| `services` | Array | IDs of services this fee applies to. |

## Example Response (Suite-based Venue)

```json
{
    "id": 1234,
    "title": "Example Venue - Suites",
    "displayName": "Example Venue",
    "logoUrl": "https://storage.tapin2.co/images/example_logo.png",
    "receiptLogoUrl": "https://storage.tapin2.co/images/example_receipt.png",
    "coords": {
        "lat": 0.000,
        "lng": 0.000
    },
    "taxRate": 7.75,
    "tipOptions": [18, 20, 22],
    "isCashless": true,
    "isAlcoholService": true,
    "fees": [
        {
            "id": 1,
            "title": "Service Fee",
            "amount": 13.0,
            "isPercentage": true,
            "isActive": true,
            "services": [1, 2, 3]
        }
    ],
    "suiteUiOptions": 25088,
    "preorderUiOptions": 0
}
```

## Venue-Specific Notes

- **Suite-based Venues**: Typically includes higher `suiteUiOptions` and multiple administrative fees specific to suite service.
- **Concessions-based Venues**: Often includes more complex `fees` structures with `offLocationIds` for specific location exclusions.


## Related Endpoints

- [Venue Locations](venue_locations.md)
- [Venue Discounts](venue_discounts.md)

---
[🔗 View Original Documentation](https://api.tapin2.co/Help/Api/GET-v2-venues-venueId-details)

[← Back to Endpoint Registry](../README.md)
