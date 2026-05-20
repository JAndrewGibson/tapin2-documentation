# GET v4/venues/{venueId}/tabs/modified/{fromDate}/{toDate}

Retrieve details for the specified endpoint.

- **Endpoint**: `v4/venues/{venueId}/tabs/modified/{fromDate}/{toDate}`
- **Method**: `GET`
- **Authentication**: Required (`Key` header)

## Parameters

| Name | Type | Located In | Description |
| :---| :---| :---| :---|
| `venueId` | Integer | Path | The parameter in path. |
| `fromDate` | String | Path | The parameter in path. |
| `toDate` | String | Path | The parameter in path. |


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
| `[].orderTaker` | String |  |
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
| `[].orders[].deviceId` | String | Unique identifier for the device. |
| `[].orders[].deviceName` | String | The name or title of the deviceName. |
| `[].orders[].orderDate` | String | Timestamp in standard formatting. |
| `[].orders[].saleDate` | String | Timestamp in standard formatting. |
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
| `[].orders[].items[].id` | Integer | Unique identifier for the record. |
| `[].orders[].items[].status` | Integer |  |
| `[].orders[].items[].locationId` | Integer | Unique identifier for the location. |
| `[].orders[].items[].location` | String |  |
| `[].orders[].items[].locationExtRefId` | Null | Unique identifier for the locationExtRef. |
| `[].orders[].items[].productId` | Integer | Unique identifier for the product. |
| `[].orders[].items[].product` | String |  |
| `[].orders[].items[].posReportingTitle` | String | The name or title of the posReportingTitle. |
| `[].orders[].items[].erpRefId` | String | Unique identifier for the erpRef. |
| `[].orders[].items[].posRefId` | String | Unique identifier for the posRef. |
| `[].orders[].items[].productType` | Integer |  |
| `[].orders[].items[].categoryId` | Integer | Unique identifier for the category. |
| `[].orders[].items[].category` | String |  |
| `[].orders[].items[].modifier` | String |  |
| `[].orders[].items[].upc` | Null |  |
| `[].orders[].items[].quantity` | Integer |  |
| `[].orders[].items[].pricePer` | Float | The price or financial value of the item. |
| `[].orders[].items[].subtotal` | Float |  |
| `[].orders[].items[].discount` | Float |  |
| `[].orders[].items[].discountCode` | String |  |
| `[].orders[].items[].barcode` | String |  |
| `[].orders[].items[].taxIncluded` | Float |  |
| `[].orders[].items[].taxAdded` | Float |  |
| `[].orders[].items[].commission` | Float |  |
| `[].orders[].items[].total` | Float |  |
| `[].orders[].items[].modifiers` | Array |  |
| `[].orders[].payments` | Array |  |
| `[].orders[].loyalty` | Array |  |
| `[].payments` | Array |  |
| `[].payments[].id` | Integer | Unique identifier for the record. |
| `[].payments[].type` | Integer |  |
| `[].payments[].gateway` | Integer |  |
| `[].payments[].ccType` | Integer |  |
| `[].payments[].transactionId` | String | Unique identifier for the transaction. |
| `[].payments[].amount` | Float |  |
| `[].payments[].tip` | Float |  |
| `[].payments[].date` | String | Timestamp in standard formatting. |
| `[].payments[].merchantReferenceCode` | String |  |
| `[].payments[].invoiceNumber` | String |  |
| `[].loyalty` | Array |  |

## Example Response (Sanitized)

```json
[
    {
        "id": 50001,
        "status": 4,
        "customer": {
            "id": 50001,
            "name": "John Doe",
            "company": "",
            "email": "customer@example.com",
            "phone": "+15555555555"
        },
        "orderTaker": "John Doe",
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
                    "id": 734,
                    "title": "Example Title"
                },
                "status": 2,
                "service": 4,
                "deviceId": "03B529F10360A551",
                "deviceName": "C - 10",
                "orderDate": "03/15/2026 5:01 AM",
                "saleDate": "03/15/2026 5:01 AM",
                "modifyDate": "04/20/2026 6:26 PM",
                "posRefId": null,
                "erpRefId": null,
                "customerId": 1755396,
                "subtotalGross": 224.0,
                "subtotalDeducted": 0.0,
                "subtotalNet": 224.0,
                "discountGross": 0.0,
                "discountDeducted": 0.0,
                "discountNet": 0.0,
                "discountCode": "",
                "feeIncludedGross": 0.0,
                "feeIncludedDeducted": 0.0,
                "feeIncludedNet": 0.0,
                "feeAddedGross": 51.52,
                "feeAddedDeducted": 0.0,
                "feeAddedNet": 51.52,
                "taxIncludedGross": 0.0,
                "taxIncludedDeducted": 0.0,
                "taxIncludedNet": 0.0,
                "taxAddedGross": 21.36,
                "taxAddedDeducted": 0.0,
                "taxAddedNet": 21.36,
                "tipGross": 0.0,
                "tipDeducted": 0.0,
                "tipNet": 0.0,
                "donationGross": 0.0,
                "donationDeducted": 0.0,
                "donationNet": 0.0,
                "totalGross": 296.88,
                "totalDeducted": 0.0,
                "totalNet": 296.88,
                "items": [
                    {
                        "id": 50001,
                        "status": 2,
                        "locationId": 2001,
                        "location": "307A GSF",
                        "locationExtRefId": null,
                        "productId": 1137983,
                        "product": "Michelob Ultra",
                        "posReportingTitle": "",
                        "erpRefId": "",
                        "posRefId": "",
                        "productType": 16,
                        "categoryId": 11725,
                        "category": "Beers",
                        "modifier": "",
                        "upc": null,
                        "quantity": 1,
                        "pricePer": 42.0,
                        "subtotal": 42.0,
                        "discount": 0.0,
                        "discountCode": "",
                        "barcode": "",
                        "taxIncluded": 0.0,
                        "taxAdded": 3.26,
                        "commission": 0.0,
                        "total": 45.26,
                        "modifiers": []
                    },
                    {
                        "id": 50001,
                        "status": 2,
                        "locationId": 2001,
                        "location": "307A GSF",
                        "locationExtRefId": null,
                        "productId": 1137989,
                        "product": "Coke Zero",
                        "posReportingTitle": "",
                        "erpRefId": "",
                        "posRefId": "",
                        "productType": 8,
                        "categoryId": 11727,
                        "category": "Beverages",
                        "modifier": "",
                        "upc": null,
                        "quantity": 1,
                        "pricePer": 28.0,
                        "subtotal": 28.0,
                        "discount": 0.0,
                        "discountCode": "",
                        "barcode": "",
                        "taxIncluded": 0.0,
                        "taxAdded": 2.17,
                        "commission": 0.0,
                        "total": 30.17,
                        "modifiers": []
                    }
                ],
                "payments": [],
                "loyalty": []
            }
        ],
        "payments": [
            {
                "id": 50001,
                "type": 65536,
                "gateway": 2,
                "ccType": 1,
                "transactionId": "01Z6NMCT7F00P811NSEENRSF3AQ8TFM6",
                "amount": 296.88,
                "tip": 0.0,
                "date": "03/15/2026 5:02 AM",
                "merchantReferenceCode": "+15555555555",
                "invoiceNumber": "+15555555555"
            },
            {
                "id": 50001,
                "type": 1,
                "gateway": 2,
                "ccType": 1,
                "transactionId": "01Z6NMCT7L00P811NSEG2H33LJ6G2VOS",
                "amount": 296.88,
                "tip": 0.0,
                "date": "03/15/2026 5:02 AM",
                "merchantReferenceCode": "+15555555555",
                "invoiceNumber": null
            }
        ],
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
        "orderTaker": "John Doe",
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
                    "id": 658,
                    "title": "Example Title"
                },
                "status": 64,
                "service": 7,
                "deviceId": null,
                "deviceName": null,
                "orderDate": "04/01/2026 7:37 PM",
                "saleDate": "04/01/2026 7:39 PM",
                "modifyDate": "04/23/2026 8:12 PM",
                "posRefId": null,
                "erpRefId": null,
                "customerId": 1704553,
                "subtotalGross": 2520.0,
                "subtotalDeducted": 2520.0,
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
                "totalGross": 2520.0,
                "totalDeducted": 2520.0,
                "totalNet": 0.0,
                "items": [
                    {
                        "id": 50001,
                        "status": 64,
                        "locationId": 2001,
                        "location": "Preorder Packages",
                        "locationExtRefId": null,
                        "productId": 1172138,
                        "product": "Classic Comforts 208 #1",
                        "posReportingTitle": "",
                        "erpRefId": null,
                        "posRefId": "",
                        "productType": 2048,
                        "categoryId": 11723,
                        "category": "Packages",
                        "modifier": "",
                        "upc": null,
                        "quantity": 1,
                        "pricePer": 840.0,
                        "subtotal": 840.0,
                        "discount": 0.0,
                        "discountCode": "",
                        "barcode": "",
                        "taxIncluded": 0.0,
                        "taxAdded": 0.0,
                        "commission": 0.0,
                        "total": 840.0,
                        "modifiers": []
                    },
                    {
                        "id": 50001,
                        "status": 64,
                        "locationId": 2001,
                        "location": "Preorder Packages",
                        "locationExtRefId": null,
                        "productId": 1172012,
                        "product": "JD Bowl Salmon PKG",
                        "posReportingTitle": "",
                        "erpRefId": null,
                        "posRefId": "",
                        "productType": 4096,
                        "categoryId": 11723,
                        "category": "Packages",
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
[🔗 View Original Documentation](https://api.tapin2.co/Help/Api/GET-v4-venues-venueId-tabs-modified-fromDate-toDate)

[← Back to Endpoint Registry](../README.md)
