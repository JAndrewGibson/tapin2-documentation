# GET v4/venues/{venueId}/events/{eventId}/tabs

Retrieve details for the specified endpoint.

- **Endpoint**: `v4/venues/{venueId}/events/{eventId}/tabs`
- **Method**: `GET`
- **Authentication**: Required (`Key` header)

## Parameters

| Name | Type | Located In | Description |
| :---| :---| :---| :---|
| `venueId` | Integer | Path | The parameter in path. |
| `eventId` | Integer | Path | The parameter in path. |


## Response Structure

| Field | Type | Description |
| :---| :---| :---|
| `[].id` | Integer | Unique identifier for the record. |
| `[].status` | Integer |  |
| `[].customer` | Object |  |
| `[].customer.id` | Integer | Unique identifier for the record. |
| `[].customer.name` | String | The name or title of the name. |
| `[].customer.company` | String |  |
| `[].customer.email` | String |  |
| `[].customer.phone` | String |  |
| `[].orderTaker` | Null |  |
| `[].orders` | Array |  |
| `[].orders[].id` | Integer | Unique identifier for the record. |
| `[].orders[].venueId` | Integer | Unique identifier for the venue. |
| `[].orders[].venueName` | String | The name or title of the venueName. |
| `[].orders[].eventId` | Integer | Unique identifier for the event. |
| `[].orders[].eventName` | String | The name or title of the eventName. |
| `[].orders[].eventType` | Object |  |
| `[].orders[].eventType.priceLevelId` | Null | Unique identifier for the priceLevel. |
| `[].orders[].eventType.customPaymentId` | Null | Unique identifier for the customPayment. |
| `[].orders[].eventType.imageUrl` | String | URL link to the resource. |
| `[].orders[].eventType.id` | Integer | Unique identifier for the record. |
| `[].orders[].eventType.title` | String | The name or title of the title. |
| `[].orders[].status` | Integer |  |
| `[].orders[].service` | Integer |  |
| `[].orders[].deviceId` | Null | Unique identifier for the device. |
| `[].orders[].deviceName` | Null | The name or title of the deviceName. |
| `[].orders[].orderDate` | String | Timestamp in standard formatting. |
| `[].orders[].saleDate` | Null | Timestamp in standard formatting. |
| `[].orders[].modifyDate` | String | Timestamp in standard formatting. |
| `[].orders[].posRefId` | Null | Unique identifier for the posRef. |
| `[].orders[].erpRefId` | Null | Unique identifier for the erpRef. |
| `[].orders[].customerId` | Integer | Unique identifier for the customer. |
| `[].orders[].subtotalGross` | Float |  |
| `[].orders[].subtotalDeducted` | Float |  |
| `[].orders[].subtotalNet` | Float |  |
| `[].orders[].discountGross` | Float |  |
| `[].orders[].discountDeducted` | Float |  |
| `[].orders[].discountNet` | Float |  |
| `[].orders[].discountCode` | String |  |
| `[].orders[].feeIncludedGross` | Float | The price or financial value of the item. |
| `[].orders[].feeIncludedDeducted` | Float | The price or financial value of the item. |
| `[].orders[].feeIncludedNet` | Float | The price or financial value of the item. |
| `[].orders[].feeAddedGross` | Float | The price or financial value of the item. |
| `[].orders[].feeAddedDeducted` | Float | The price or financial value of the item. |
| `[].orders[].feeAddedNet` | Float | The price or financial value of the item. |
| `[].orders[].taxIncludedGross` | Float |  |
| `[].orders[].taxIncludedDeducted` | Float |  |
| `[].orders[].taxIncludedNet` | Float |  |
| `[].orders[].taxAddedGross` | Float |  |
| `[].orders[].taxAddedDeducted` | Float |  |
| `[].orders[].taxAddedNet` | Float |  |
| `[].orders[].tipGross` | Float |  |
| `[].orders[].tipDeducted` | Float |  |
| `[].orders[].tipNet` | Float |  |
| `[].orders[].donationGross` | Float |  |
| `[].orders[].donationDeducted` | Float |  |
| `[].orders[].donationNet` | Float |  |
| `[].orders[].totalGross` | Float |  |
| `[].orders[].totalDeducted` | Float |  |
| `[].orders[].totalNet` | Float |  |
| `[].orders[].items` | Array |  |
| `[].orders[].payments` | Array |  |
| `[].orders[].loyalty` | Array |  |
| `[].payments` | Array |  |
| `[].loyalty` | Array |  |

## Example Response (Sanitized)

```json
[
    {
        "id": 50001,
        "status": 1,
        "customer": {
            "id": 50001,
            "name": "John Doe",
            "company": "",
            "email": "customer@example.com",
            "phone": "+15555555555"
        },
        "orderTaker": null,
        "orders": [
            {
                "id": 50001,
                "venueId": 1001,
                "venueName": "Example Venue",
                "eventId": 3001,
                "eventName": "Event ABC",
                "eventType": {
                    "priceLevelId": null,
                    "customPaymentId": null,
                    "imageUrl": "",
                    "id": 657,
                    "title": "Example Title"
                },
                "status": 1,
                "service": 7,
                "deviceId": null,
                "deviceName": null,
                "orderDate": "02/23/2026 11:20 PM",
                "saleDate": null,
                "modifyDate": "02/23/2026 11:20 PM",
                "posRefId": null,
                "erpRefId": null,
                "customerId": 2001600,
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
        ],
        "payments": [],
        "loyalty": []
    },
    {
        "id": 50001,
        "status": 1,
        "customer": {
            "id": 50001,
            "name": "John Doe",
            "company": "",
            "email": "customer@example.com",
            "phone": "+15555555555"
        },
        "orderTaker": null,
        "orders": [
            {
                "id": 50001,
                "venueId": 1001,
                "venueName": "Example Venue",
                "eventId": 3001,
                "eventName": "Event ABC",
                "eventType": {
                    "priceLevelId": null,
                    "customPaymentId": null,
                    "imageUrl": "",
                    "id": 657,
                    "title": "Example Title"
                },
                "status": 1,
                "service": 7,
                "deviceId": null,
                "deviceName": null,
                "orderDate": "02/25/2026 5:29 PM",
                "saleDate": null,
                "modifyDate": "02/25/2026 5:29 PM",
                "posRefId": null,
                "erpRefId": null,
                "customerId": 1741331,
                "subtotalGross": 973.0,
                "subtotalDeducted": 0.0,
                "subtotalNet": 973.0,
                "discountGross": 0.0,
                "discountDeducted": 0.0,
                "discountNet": 0.0,
                "discountCode": "",
                "feeIncludedGross": 0.0,
                "feeIncludedDeducted": 0.0,
                "feeIncludedNet": 0.0,
                "feeAddedGross": 223.79,
                "feeAddedDeducted": 0.0,
                "feeAddedNet": 223.79,
                "taxIncludedGross": 0.0,
                "taxIncludedDeducted": 0.0,
                "taxIncludedNet": 0.0,
                "taxAddedGross": 92.76,
                "taxAddedDeducted": 0.0,
                "taxAddedNet": 92.76,
                "tipGross": 0.0,
                "tipDeducted": 0.0,
                "tipNet": 0.0,
                "donationGross": 0.0,
                "donationDeducted": 0.0,
                "donationNet": 0.0,
                "totalGross": 1289.55,
                "totalDeducted": 0.0,
                "totalNet": 1289.55,
                "items": [
                    {
                        "id": 50001,
                        "status": 1,
                        "locationId": 2001,
                        "location": "Preorder",
                        "locationExtRefId": null,
                        "productId": 1162977,
                        "product": "Mucho Munchies",
                        "posReportingTitle": "",
                        "erpRefId": "",
                        "posRefId": "",
                        "productType": 1,
                        "categoryId": 11724,
                        "category": "A La Carte",
                        "modifier": "",
                        "upc": null,
                        "quantity": 1,
                        "pricePer": 35.0,
                        "subtotal": 35.0,
                        "discount": 0.0,
                        "discountCode": "",
                        "barcode": "",
                        "taxIncluded": 0.0,
                        "taxAdded": 2.71,
                        "commission": 0.0,
                        "total": 37.71,
                        "modifiers": []
                    },
                    {
                        "id": 50001,
                        "status": 1,
                        "locationId": 2001,
                        "location": "Preorder",
                        "locationExtRefId": null,
                        "productId": 1162978,
                        "product": "Kettle Chips",
                        "posReportingTitle": "",
                        "erpRefId": null,
                        "posRefId": "",
                        "productType": 4096,
                        "categoryId": 11724,
                        "category": "A La Carte",
                        "modifier": "",
                        "upc": null,
                        "quantity": 1,
                        "pricePer": 0.0,
                        "subtotal": 0.0,
                        "discount": 0.0,
                        "discountCode": "",
                        "barcode": "",
                        "taxIncluded": 0.0,
                        "taxAdded": 0.0,
                        "commission": 0.0,
                        "total": 0.0,
                        "modifiers": []
                    }
                ],
                "payments": [],
                "loyalty": []
            }
        ],
        "payments": [],
        "loyalty": []
    }
]
```

## Venue-Specific Notes

- **Sandbox Status**: Active and functional.
- **Payload Size**: The live sandbox returns a valid data payload.

---
[🔗 View Original Documentation](https://api.tapin2.co/Help/Api/GET-v4-venues-venueId-events-eventId-tabs)

[← Back to Endpoint Registry](../README.md)
