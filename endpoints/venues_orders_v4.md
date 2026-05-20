# GET v4/venues/{venueId}/orders/{orderId}

Retrieve details for the specified endpoint.

- **Endpoint**: `v4/venues/{venueId}/orders/{orderId}`
- **Method**: `GET`
- **Authentication**: Required (`Key` header)

## Parameters

| Name | Type | Located In | Description |
| :---| :---| :---| :---|
| `venueId` | Integer | Path | The parameter in path. |
| `orderId` | Integer | Path | The parameter in path. |


## Response Structure

| Field | Type | Description |
| :---| :---| :---|
| `[].id` | Integer | Unique identifier for the record. |
| `[].venueId` | Integer | Unique identifier for the venue. |
| `[].venueName` | String | The name or title of the venueName. |
| `[].eventId` | Integer | Unique identifier for the event. |
| `[].eventName` | String | The name or title of the eventName. |
| `[].eventType` | Object |  |
| `[].eventType.priceLevelId` | Integer | Unique identifier for the priceLevel. |
| `[].eventType.customPaymentId` | Null | Unique identifier for the customPayment. |
| `[].eventType.imageUrl` | String | URL link to the resource. |
| `[].eventType.id` | Integer | Unique identifier for the record. |
| `[].eventType.title` | String | The name or title of the title. |
| `[].status` | Integer |  |
| `[].service` | Integer |  |
| `[].deviceId` | String | Unique identifier for the device. |
| `[].deviceName` | String | The name or title of the deviceName. |
| `[].orderDate` | String | Timestamp in standard formatting. |
| `[].saleDate` | Null | Timestamp in standard formatting. |
| `[].modifyDate` | String | Timestamp in standard formatting. |
| `[].posRefId` | Null | Unique identifier for the posRef. |
| `[].erpRefId` | Null | Unique identifier for the erpRef. |
| `[].customerId` | Null | Unique identifier for the customer. |
| `[].subtotalGross` | Float |  |
| `[].subtotalDeducted` | Float |  |
| `[].subtotalNet` | Float |  |
| `[].discountGross` | Float |  |
| `[].discountDeducted` | Float |  |
| `[].discountNet` | Float |  |
| `[].discountCode` | String |  |
| `[].feeIncludedGross` | Float | The price or financial value of the item. |
| `[].feeIncludedDeducted` | Float | The price or financial value of the item. |
| `[].feeIncludedNet` | Float | The price or financial value of the item. |
| `[].feeAddedGross` | Float | The price or financial value of the item. |
| `[].feeAddedDeducted` | Float | The price or financial value of the item. |
| `[].feeAddedNet` | Float | The price or financial value of the item. |
| `[].taxIncludedGross` | Float |  |
| `[].taxIncludedDeducted` | Float |  |
| `[].taxIncludedNet` | Float |  |
| `[].taxAddedGross` | Float |  |
| `[].taxAddedDeducted` | Float |  |
| `[].taxAddedNet` | Float |  |
| `[].tipGross` | Float |  |
| `[].tipDeducted` | Float |  |
| `[].tipNet` | Float |  |
| `[].donationGross` | Float |  |
| `[].donationDeducted` | Float |  |
| `[].donationNet` | Float |  |
| `[].totalGross` | Float |  |
| `[].totalDeducted` | Float |  |
| `[].totalNet` | Float |  |
| `[].items` | Array |  |
| `[].payments` | Array |  |
| `[].loyalty` | Array |  |

## Example Response (Sanitized)

```json
[
    {
        "id": 50001,
        "venueId": 1001,
        "venueName": "Example Venue",
        "eventId": 3001,
        "eventName": "Event ABC",
        "eventType": {
            "priceLevelId": 23,
            "customPaymentId": null,
            "imageUrl": "",
            "id": 40,
            "title": "Example Title"
        },
        "status": 1,
        "service": 3,
        "deviceId": "A233A62913",
        "deviceName": "408 Kiosk 02",
        "orderDate": "04/29/2026 10:27 PM",
        "saleDate": null,
        "modifyDate": "04/29/2026 10:27 PM",
        "posRefId": null,
        "erpRefId": null,
        "customerId": null,
        "subtotalGross": 0.0,
        "subtotalDeducted": 0.0,
        "subtotalNet": 0.0,
        "discountGross": 0.0,
        "discountDeducted": 0.0,
        "discountNet": 0.0,
        "discountCode": "",
        "feeIncludedGross": 0.0,
        "feeIncludedDeducted": 0.0,
        "feeIncludedNet": 0.0,
        "feeAddedGross": 0.0,
        "feeAddedDeducted": 0.0,
        "feeAddedNet": 0.0,
        "taxIncludedGross": 0.0,
        "taxIncludedDeducted": 0.0,
        "taxIncludedNet": 0.0,
        "taxAddedGross": 0.0,
        "taxAddedDeducted": 0.0,
        "taxAddedNet": 0.0,
        "tipGross": 0.0,
        "tipDeducted": 0.0,
        "tipNet": 0.0,
        "donationGross": 0.0,
        "donationDeducted": 0.0,
        "donationNet": 0.0,
        "totalGross": 0.0,
        "totalDeducted": 0.0,
        "totalNet": 0.0,
        "items": [],
        "payments": [],
        "loyalty": []
    }
]
```

## Venue-Specific Notes

- **Sandbox Status**: Active and functional.
- **Payload Size**: The live sandbox returns a valid data payload.

---
[🔗 View Original Documentation](https://api.tapin2.co/Help/Api/GET-v4-venues-venueId-orders-orderId)

[← Back to Endpoint Registry](../README.md)
