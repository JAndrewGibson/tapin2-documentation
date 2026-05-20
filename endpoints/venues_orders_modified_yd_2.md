# GET yd/venues/{venueId}/orders/modified/{fromDate}/{fromMins}/{toDate}/{toMins}

Retrieve details for the specified endpoint.

- **Endpoint**: `yd/venues/{venueId}/orders/modified/{fromDate}/{fromMins}/{toDate}/{toMins}?addDayToEndOfRange={addDayToEndOfRange}`
- **Method**: `GET`
- **Authentication**: Required (`Key` header)

## Parameters

| Name | Type | Located In | Description |
| :---| :---| :---| :---|
| `venueId` | Integer | Path | The parameter in path. |
| `fromDate` | String | Path | The parameter in path. |
| `fromMins` | String | Path | The parameter in path. |
| `toDate` | String | Path | The parameter in path. |
| `toMins` | String | Path | The parameter in path. |
| `addDayToEndOfRange` | Boolean | Query | Optional query parameter. |


## Response Structure

| Field | Type | Description |
| :---| :---| :---|
| `[].id` | Integer | Unique identifier for the record. |
| `[].orderStatus` | Integer |  |
| `[].locationId` | Integer | Unique identifier for the location. |
| `[].service` | Integer |  |
| `[].venueId` | Integer | Unique identifier for the venue. |
| `[].orderDate` | String | Timestamp in standard formatting. |
| `[].saleDate` | String | Timestamp in standard formatting. |
| `[].fulfillmentDate` | Null | Timestamp in standard formatting. |
| `[].modifyDate` | String | Timestamp in standard formatting. |
| `[].orderDeviceId` | Integer | Unique identifier for the orderDevice. |
| `[].fulfillDeviceId` | Null | Unique identifier for the fulfillDevice. |
| `[].taxes` | Array |  |
| `[].payments` | Array |  |
| `[].payments[].type` | Integer |  |
| `[].payments[].amount` | Float |  |
| `[].gratuity` | Float |  |
| `[].fees` | Array | The price or financial value of the item. |
| `[].items` | Array |  |
| `[].items[].id` | Integer | Unique identifier for the record. |
| `[].items[].product` | Object |  |
| `[].items[].product.id` | Integer | Unique identifier for the record. |
| `[].items[].product.title` | String | The name or title of the title. |
| `[].items[].product.externalRefId` | String | Unique identifier for the externalRef. |
| `[].items[].pricePer` | Float | The price or financial value of the item. |
| `[].items[].quantity` | Integer |  |
| `[].items[].discount` | Float |  |
| `[].items[].discountCode` | String |  |
| `[].items[].isVoid` | Boolean | Unique identifier for the record. |
| `[].items[].isReturn` | Boolean |  |
| `[].items[].isRefund` | Boolean |  |
| `[].items[].modifiers` | Array |  |

## Example Response (Sanitized)

```json
[
    {
        "id": 50001,
        "orderStatus": 2,
        "locationId": 2001,
        "service": 9,
        "venueId": 1001,
        "orderDate": "04/05/2026 12:46 AM",
        "saleDate": "04/05/2026 12:47 AM",
        "fulfillmentDate": null,
        "modifyDate": "05/01/2026 5:04 AM",
        "orderDeviceId": 7842,
        "fulfillDeviceId": null,
        "taxes": [],
        "payments": [
            {
                "type": 1,
                "amount": 30.17
            },
            {
                "type": 1,
                "amount": -30.17
            }
        ],
        "gratuity": 0.0,
        "fees": [],
        "items": [
            {
                "id": 50001,
                "product": {
                    "id": 50001,
                    "title": "Example Title",
                    "externalRefId": "+15555555555"
                },
                "pricePer": 28.0,
                "quantity": 1,
                "discount": 0.0,
                "discountCode": "",
                "isVoid": false,
                "isReturn": false,
                "isRefund": false,
                "modifiers": []
            },
            {
                "id": 50001,
                "product": {
                    "id": 50001,
                    "title": "Example Title",
                    "externalRefId": "+15555555555"
                },
                "pricePer": 28.0,
                "quantity": -1,
                "discount": 0.0,
                "discountCode": "",
                "isVoid": true,
                "isReturn": true,
                "isRefund": true,
                "modifiers": []
            }
        ]
    },
    {
        "id": 50001,
        "orderStatus": 32,
        "locationId": 2001,
        "service": 3,
        "venueId": 1001,
        "orderDate": "04/12/2026 11:05 PM",
        "saleDate": "04/12/2026 11:06 PM",
        "fulfillmentDate": "04/12/2026 11:07 PM",
        "modifyDate": "04/25/2026 2:31 AM",
        "orderDeviceId": 6461,
        "fulfillDeviceId": 2987,
        "taxes": [],
        "payments": [
            {
                "type": 1,
                "amount": 26.56
            },
            {
                "type": 1,
                "amount": -26.56
            }
        ],
        "gratuity": 0.0,
        "fees": [],
        "items": [
            {
                "id": 50001,
                "product": {
                    "id": 50001,
                    "title": "Example Title",
                    "externalRefId": "+15555555555"
                },
                "pricePer": 21.0,
                "quantity": 1,
                "discount": 3.15,
                "discountCode": "",
                "isVoid": false,
                "isReturn": false,
                "isRefund": false,
                "modifiers": []
            },
            {
                "id": 50001,
                "product": {
                    "id": 624839,
                    "title": "Example Title",
                    "externalRefId": "624839"
                },
                "pricePer": 8.0,
                "quantity": 1,
                "discount": 1.2,
                "discountCode": "",
                "isVoid": false,
                "isReturn": false,
                "isRefund": false,
                "modifiers": [
                    {
                        "id": 50001,
                        "title": "Example Title",
                        "priceDiff": 0.0
                    }
                ]
            }
        ]
    }
]
```

## Venue-Specific Notes

- **Sandbox Status**: Active and functional.
- **Payload Size**: The live sandbox returns a valid data payload.

---
[🔗 View Original Documentation](https://api.tapin2.co/Help/Api/GET-yd-venues-venueId-orders-modified-fromDate-fromMins-toDate-toMins)

[← Back to Endpoint Registry](../README.md)
