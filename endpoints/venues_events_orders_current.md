# GET v2/venues/{venueId}/events/{eventId}/orders/{seatId}/current

Retrieve details for the specified endpoint.

- **Endpoint**: `v2/venues/{venueId}/events/{eventId}/orders/{seatId}/current`
- **Method**: `GET`
- **Authentication**: Required (`Key` header)

## Parameters

| Name | Type | Located In | Description |
| :---| :---| :---| :---|
| `venueId` | Integer | Path | The parameter in path. |
| `eventId` | Integer | Path | The parameter in path. |
| `seatId` | Integer | Path | The parameter in path. |


## Response Structure

| Field | Type | Description |
| :---| :---| :---|
| `id` | Integer | Unique identifier for the record. |
| `idLast3` | String | Unique identifier for the record. |
| `venue` | Object |  |
| `venue.displayName` | String | The name or title of the displayName. |
| `venue.coords` | Object |  |
| `venue.coords.lat` | Float |  |
| `venue.coords.lng` | Float |  |
| `venue.timeZoneInfo` | Object | Timestamp in standard formatting. |
| `venue.timeZoneInfo.Id` | String | Unique identifier for the . |
| `venue.timeZoneInfo.DisplayName` | String | The name or title of the DisplayName. |
| `venue.timeZoneInfo.StandardName` | String | The name or title of the StandardName. |
| `venue.timeZoneInfo.DaylightName` | String | The name or title of the DaylightName. |
| `venue.timeZoneInfo.BaseUtcOffset` | String |  |
| `venue.timeZoneInfo.AdjustmentRules` | Array |  |
| `venue.timeZoneInfo.AdjustmentRules[].DateStart` | String | Timestamp in standard formatting. |
| `venue.timeZoneInfo.AdjustmentRules[].DateEnd` | String | Timestamp in standard formatting. |
| `venue.timeZoneInfo.AdjustmentRules[].DaylightDelta` | String |  |
| `venue.timeZoneInfo.AdjustmentRules[].DaylightTransitionStart` | Object |  |
| `venue.timeZoneInfo.AdjustmentRules[].DaylightTransitionStart.TimeOfDay` | String | Timestamp in standard formatting. |
| `venue.timeZoneInfo.AdjustmentRules[].DaylightTransitionStart.Month` | Integer |  |
| `venue.timeZoneInfo.AdjustmentRules[].DaylightTransitionStart.Week` | Integer |  |
| `venue.timeZoneInfo.AdjustmentRules[].DaylightTransitionStart.Day` | Integer |  |
| `venue.timeZoneInfo.AdjustmentRules[].DaylightTransitionStart.DayOfWeek` | Integer |  |
| `venue.timeZoneInfo.AdjustmentRules[].DaylightTransitionStart.IsFixedDateRule` | Boolean | Timestamp in standard formatting. |
| `venue.timeZoneInfo.AdjustmentRules[].DaylightTransitionEnd` | Object |  |
| `venue.timeZoneInfo.AdjustmentRules[].DaylightTransitionEnd.TimeOfDay` | String | Timestamp in standard formatting. |
| `venue.timeZoneInfo.AdjustmentRules[].DaylightTransitionEnd.Month` | Integer |  |
| `venue.timeZoneInfo.AdjustmentRules[].DaylightTransitionEnd.Week` | Integer |  |
| `venue.timeZoneInfo.AdjustmentRules[].DaylightTransitionEnd.Day` | Integer |  |
| `venue.timeZoneInfo.AdjustmentRules[].DaylightTransitionEnd.DayOfWeek` | Integer |  |
| `venue.timeZoneInfo.AdjustmentRules[].DaylightTransitionEnd.IsFixedDateRule` | Boolean | Timestamp in standard formatting. |
| `venue.timeZoneInfo.AdjustmentRules[].BaseUtcOffsetDelta` | String |  |
| `venue.timeZoneInfo.SupportsDaylightSavingTime` | Boolean | Timestamp in standard formatting. |
| `venue.priceIncludesFee` | Boolean | The price or financial value of the item. |
| `venue.taxRate` | Float |  |
| `venue.taxParts` | Array |  |
| `venue.archived` | Boolean |  |
| `venue.priceIncludesTax` | Boolean | The price or financial value of the item. |
| `venue.tipOptions` | Array |  |
| `venue.eventStartAdjustment` | String |  |
| `venue.type` | Integer |  |
| `venue.priceLevelEnabled` | Boolean | The price or financial value of the item. |
| `venue.deliveryMethod` | Integer |  |
| `venue.kioskTimeouts` | Array | Timestamp in standard formatting. |
| `venue.kioskUiOptions` | Integer |  |
| `venue.mobileUiOptions2` | Integer |  |
| `venue.adminUiOptions` | Integer |  |
| `venue.mobileUiOptions` | Integer |  |
| `venue.hawkerUiOptions` | Integer |  |
| `venue.orderTakerUiOptions` | Integer |  |
| `venue.orderTakerUiOptions2` | Integer |  |
| `venue.suiteUiOptions` | Integer |  |
| `venue.suiteUiOptions2` | Integer |  |
| `venue.suiteUiOptions3` | Integer |  |
| `venue.preorderUiOptions` | Integer |  |
| `venue.preorderUiOptions2` | Integer |  |
| `venue.terminalUiOptions` | Integer |  |
| `venue.maxAlcoholPerOrder` | Null |  |
| `venue.discountIncludesAlcohol` | Boolean |  |
| `venue.fees` | Array | The price or financial value of the item. |
| `venue.fees[].description` | String |  |
| `venue.fees[].amount` | Float |  |
| `venue.fees[].amountString` | String |  |
| `venue.fees[].isPercentage` | Boolean |  |
| `venue.fees[].isPickup` | Boolean |  |
| `venue.fees[].isSubjectToTax` | Boolean |  |
| `venue.fees[].isPreDiscount` | Boolean |  |
| `venue.fees[].isCustom` | Boolean |  |
| `venue.fees[].isPerOrder` | Boolean |  |
| `venue.fees[].isActive` | Boolean | Indicates whether the record is currently active. |
| `venue.fees[].isExemptWhenFullyDiscounted` | Boolean |  |
| `venue.fees[].services` | Array |  |
| `venue.fees[].offLocationIds` | Array | Unique identifier for the record. |
| `venue.fees[].id` | Integer | Unique identifier for the record. |
| `venue.fees[].title` | String | The name or title of the title. |
| `venue.id` | Integer | Unique identifier for the record. |
| `venue.title` | String | The name or title of the title. |
| `venueId` | Integer | Unique identifier for the venue. |
| `event` | Object |  |
| `event.startDate` | String | Timestamp in standard formatting. |
| `event.orderingStartDate` | String | Timestamp in standard formatting. |
| `event.endDate` | String | Timestamp in standard formatting. |
| `event.taxExempt` | Boolean |  |
| `event.includeInReports` | Boolean |  |
| `event.address` | String |  |
| `event.lastCallDate` | Null | Timestamp in standard formatting. |
| `event.isLastCall` | Boolean |  |
| `event.isCurrent` | Boolean |  |
| `event.eventType` | Object |  |
| `event.eventType.priceLevelId` | Integer | Unique identifier for the priceLevel. |
| `event.eventType.customPaymentId` | Null | Unique identifier for the customPayment. |
| `event.eventType.imageUrl` | String | URL link to the resource. |
| `event.eventType.id` | Integer | Unique identifier for the record. |
| `event.eventType.title` | String | The name or title of the title. |
| `event.id` | Integer | Unique identifier for the record. |
| `event.title` | String | The name or title of the title. |
| `eventId` | Integer | Unique identifier for the event. |
| `seatId` | Integer | Unique identifier for the seat. |
| `seat` | Object |  |
| `seat.title` | String | The name or title of the title. |
| `seat.section` | Object |  |
| `seat.section.group` | Object |  |
| `seat.section.group.id` | Integer | Unique identifier for the record. |
| `seat.section.group.title` | String | The name or title of the title. |
| `seat.section.rowTitle` | String | The name or title of the rowTitle. |
| `seat.section.numberTitle` | String | The name or title of the numberTitle. |
| `seat.section.sectionRefId` | Null | Unique identifier for the sectionRef. |
| `seat.section.id` | Integer | Unique identifier for the record. |
| `seat.section.title` | String | The name or title of the title. |
| `seat.row` | String |  |
| `seat.number` | String |  |
| `seat.description` | String |  |
| `seat.isActive` | Boolean | Indicates whether the record is currently active. |
| `seat.sectionRowTitle` | String | The name or title of the sectionRowTitle. |
| `seat.longTitle` | String | The name or title of the longTitle. |
| `seat.id` | Integer | Unique identifier for the record. |
| `hasSeat` | Boolean |  |
| `pagerNumber` | Null |  |
| `deliveryAppRefId` | Null | Unique identifier for the deliveryAppRef. |
| `orderStatus` | Integer |  |
| `deliveryMethod` | Integer |  |
| `menuMethod` | Integer |  |
| `service` | Integer |  |
| `serviceString` | String |  |
| `deviceId` | Null | Unique identifier for the device. |
| `device` | Null |  |
| `fulfillmentDeviceId` | Null | Unique identifier for the fulfillmentDevice. |
| `fulfillmentDevice` | Null |  |
| `userId` | Null | Unique identifier for the user. |
| `locationId` | Null | Unique identifier for the location. |
| `location` | Null |  |
| `runnerId` | Null | Unique identifier for the runner. |
| `orderDate` | String | Timestamp in standard formatting. |
| `userInfo` | Object |  |
| `userInfo.name` | String | The name or title of the name. |
| `userInfo.email` | String |  |
| `userInfo.phone` | String |  |
| `userInfo.company` | String |  |
| `userInfo.booth` | String |  |
| `userInfo.subscribe` | Boolean |  |
| `userInfo.dob` | String |  |
| `userInfo.customerId` | Null | Unique identifier for the customer. |
| `userInfo.ageVerified` | Boolean |  |
| `exemptTaxPartIds` | Null | Unique identifier for the record. |
| `feeFlat` | Float | The price or financial value of the item. |
| `feePercentage` | Float | The price or financial value of the item. |
| `feeExists` | Boolean | The price or financial value of the item. |
| `subtotalGross` | Float |  |
| `subtotalDeducted` | Float |  |
| `subtotalNet` | Float |  |
| `discountId` | Null | Unique identifier for the discount. |
| `discount` | Null |  |
| `discountCode` | String |  |
| `discountGross` | Float |  |
| `discountDeducted` | Float |  |
| `discountNet` | Float |  |
| `feeIncludedGross` | Float | The price or financial value of the item. |
| `feeIncludedDeducted` | Float | The price or financial value of the item. |
| `feeIncludedNet` | Float | The price or financial value of the item. |
| `feeAddedGross` | Float | The price or financial value of the item. |
| `feeAddedDeducted` | Float | The price or financial value of the item. |
| `feeAddedNet` | Float | The price or financial value of the item. |
| `taxIncludedGross` | Float |  |
| `taxIncludedDeducted` | Float |  |
| `taxIncludedNet` | Float |  |
| `taxAddedGross` | Float |  |
| `taxAddedDeducted` | Float |  |
| `taxAddedNet` | Float |  |
| `tipGross` | Float |  |
| `tipDeducted` | Float |  |
| `tipNet` | Float |  |
| `donationGross` | Float |  |
| `donationDeducted` | Float |  |
| `donationNet` | Float |  |
| `totalGross` | Float |  |
| `totalGrossMinusTips` | Float |  |
| `totalDeducted` | Float |  |
| `totalNet` | Float |  |
| `note` | String |  |
| `guid` | String | Unique identifier for the record. |
| `saleDate` | Null | Timestamp in standard formatting. |
| `printDate` | Null | Timestamp in standard formatting. |
| `claimedDate` | Null | Timestamp in standard formatting. |
| `lastInboundSmsDate` | Null | Timestamp in standard formatting. |
| `prepDate` | Null | Timestamp in standard formatting. |
| `outDate` | Null | Timestamp in standard formatting. |
| `deliveryDate` | Null | Timestamp in standard formatting. |
| `scheduleDate` | Null | Timestamp in standard formatting. |
| `satisfactionSentDate` | Null | Timestamp in standard formatting. |
| `lastCallSentDate` | Null | Timestamp in standard formatting. |
| `followUpSentDate` | Null | Timestamp in standard formatting. |
| `satisfaction` | Null |  |
| `lastDeliveryAttempt` | Null |  |
| `deliveryAttempts` | Integer |  |
| `tabId` | Null | Unique identifier for the tab. |
| `posStatus` | Null |  |
| `posLastUpdated` | Null | Timestamp in standard formatting. |
| `waiveFees` | Boolean | The price or financial value of the item. |
| `taxExempt` | Boolean |  |
| `priceLevelId` | Null | Unique identifier for the priceLevel. |
| `options` | Integer |  |
| `fulfillmentTimeId` | Null | Unique identifier for the fulfillmentTime. |
| `posRefId` | Null | Unique identifier for the posRef. |
| `posErrorDetails` | Null |  |
| `erpStatus` | Null |  |
| `erpRefId` | Null | Unique identifier for the erpRef. |
| `erpErrorDetails` | Null |  |
| `orderingAppStatus` | Null |  |
| `orderingAppRefId` | Null | Unique identifier for the orderingAppRef. |
| `orderingAppErrorDetails` | Null |  |
| `loyaltyRefId` | Null | Unique identifier for the loyaltyRef. |
| `modifyDate` | String | Timestamp in standard formatting. |
| `queueId` | Integer | Unique identifier for the queue. |
| `noItemsRemoved` | Boolean |  |
| `unvoidedItems` | Array | Unique identifier for the record. |
| `items` | Array |  |
| `modifiersByItem` | Null |  |
| `payments` | Array |  |
| `loyalty` | Array |  |
| `address` | Object |  |
| `address.street1` | String |  |
| `address.street2` | String |  |
| `address.city` | String |  |
| `address.state` | String |  |
| `address.zip` | String |  |
| `address.country` | String |  |
| `statusList` | Object |  |
| `statusList.admin` | Integer |  |
| `statusList.mobile` | Integer |  |
| `statusList.kiosk` | Integer |  |
| `statusList.orderTaker` | Integer |  |
| `statusList.hawker` | Integer |  |
| `statusList.suite` | Integer |  |
| `statusList.preorder` | Integer |  |
| `statusList.fulfill` | Integer |  |
| `statusList.terminal` | Integer |  |
| `nextStatus` | Integer |  |
| `previousStatus` | Integer |  |
| `hasRunnerStatus` | Boolean |  |
| `sendToRunner` | Boolean |  |
| `distinctLocations` | Array |  |
| `fromSms` | String |  |
| `fromEmail` | String |  |
| `discountErrorMessage` | Null |  |
| `cultureId` | String | Unique identifier for the culture. |
| `notes` | Object |  |
| `receiptUrl` | String | URL link to the resource. |
| `taxParts` | Object |  |
| `itemTaxParts` | Object |  |
| `fees` | Object | The price or financial value of the item. |
| `answers` | Array |  |
| `containsAlcohol` | Boolean |  |
| `isPaidInFull` | Boolean | Unique identifier for the record. |

## Example Response (Sanitized)

```json
{
    "id": 50001,
    "idLast3": "188",
    "venue": {
        "displayName": "Example Venue",
        "coords": {
            "lat": 33.807907,
            "lng": -117.876746
        },
        "timeZoneInfo": {
            "Id": "Pacific Standard Time",
            "DisplayName": "(UTC-08:00) Pacific Time (US & Canada)",
            "StandardName": "Pacific Standard Time",
            "DaylightName": "Pacific Daylight Time",
            "BaseUtcOffset": "-08:00:00",
            "AdjustmentRules": [
                {
                    "DateStart": "01/01/0001 12:00 AM",
                    "DateEnd": "12/31/2006 12:00 AM",
                    "DaylightDelta": "01:00:00",
                    "DaylightTransitionStart": {
                        "TimeOfDay": "01/01/0001 2:00 AM",
                        "Month": 4,
                        "Week": 1,
                        "Day": 1,
                        "DayOfWeek": 0,
                        "IsFixedDateRule": false
                    },
                    "DaylightTransitionEnd": {
                        "TimeOfDay": "01/01/0001 2:00 AM",
                        "Month": 10,
                        "Week": 5,
                        "Day": 1,
                        "DayOfWeek": 0,
                        "IsFixedDateRule": false
                    },
                    "BaseUtcOffsetDelta": "00:00:00"
                },
                {
                    "DateStart": "01/01/2007 12:00 AM",
                    "DateEnd": "12/31/9999 12:00 AM",
                    "DaylightDelta": "01:00:00",
                    "DaylightTransitionStart": {
                        "TimeOfDay": "01/01/0001 2:00 AM",
                        "Month": 3,
                        "Week": 2,
                        "Day": 1,
                        "DayOfWeek": 0,
                        "IsFixedDateRule": false
                    },
                    "DaylightTransitionEnd": {
                        "TimeOfDay": "01/01/0001 2:00 AM",
                        "Month": 11,
                        "Week": 1,
                        "Day": 1,
                        "DayOfWeek": 0,
                        "IsFixedDateRule": false
                    },
                    "BaseUtcOffsetDelta": "00:00:00"
                }
            ],
            "SupportsDaylightSavingTime": true
        },
        "priceIncludesFee": false,
        "taxRate": 7.75,
        "taxParts": [],
        "archived": false,
        "priceIncludesTax": false,
        "tipOptions": [
            18,
            20
        ],
        "eventStartAdjustment": "01:30:00",
        "type": 4,
        "priceLevelEnabled": true,
        "deliveryMethod": 3,
        "kioskTimeouts": [
            40,
            20
        ],
        "kioskUiOptions": 16393,
        "mobileUiOptions2": 100359,
        "adminUiOptions": 0,
        "mobileUiOptions": 1160919185,
        "hawkerUiOptions": 0,
        "orderTakerUiOptions": 268436487,
        "orderTakerUiOptions2": 3,
        "suiteUiOptions": 404750390,
        "suiteUiOptions2": 8437800,
        "suiteUiOptions3": 82,
        "preorderUiOptions": 537395201,
        "preorderUiOptions2": 1296,
        "terminalUiOptions": 579,
        "maxAlcoholPerOrder": null,
        "discountIncludesAlcohol": true,
        "fees": [
            {
                "description": "Example Title",
                "amount": 18.0,
                "amountString": "18.00%",
                "isPercentage": true,
                "isPickup": false,
                "isSubjectToTax": true,
                "isPreDiscount": false,
                "isCustom": false,
                "isPerOrder": true,
                "isActive": false,
                "isExemptWhenFullyDiscounted": false,
                "services": [],
                "offLocationIds": [],
                "id": 96,
                "title": "Example Title"
            },
            {
                "description": "Example Title",
                "amount": 18.0,
                "amountString": "18.00%",
                "isPercentage": true,
                "isPickup": false,
                "isSubjectToTax": true,
                "isPreDiscount": true,
                "isCustom": false,
                "isPerOrder": true,
                "isActive": false,
                "isExemptWhenFullyDiscounted": false,
                "services": [
                    2,
                    6
                ],
                "offLocationIds": [],
                "id": 200,
                "title": "Example Title"
            }
        ],
        "id": 1001,
        "title": "Example Venue"
    },
    "venueId": 1001,
    "event": {
        "startDate": "04/29/2026 5:00 PM",
        "orderingStartDate": "04/29/2026 3:30 PM",
        "endDate": "04/30/2026 12:30 AM",
        "taxExempt": false,
        "includeInReports": true,
        "address": "",
        "lastCallDate": null,
        "isLastCall": true,
        "isCurrent": false,
        "eventType": {
            "priceLevelId": 23,
            "customPaymentId": null,
            "imageUrl": "",
            "id": 40,
            "title": "Example Title"
        },
        "id": 3001,
        "title": "Example Title"
    },
    "eventId": 3001,
    "seatId": 4001,
    "seat": {
        "title": "Example Title",
        "section": {
            "group": {
                "id": 130,
                "title": "Example Title"
            },
            "rowTitle": "",
            "numberTitle": "",
            "sectionRefId": null,
            "id": 21968,
            "title": "Example Title"
        },
        "row": "D",
        "number": "5",
        "description": "Example Title",
        "isActive": true,
        "sectionRowTitle": "Sec 305, Row D",
        "longTitle": "Sec 305, Row D, Seat 5",
        "id": 50001
    },
    "hasSeat": true,
    "pagerNumber": null,
    "deliveryAppRefId": null,
    "orderStatus": 1,
    "deliveryMethod": 1,
    "menuMethod": 4,
    "service": 2,
    "serviceString": "Mobile",
    "deviceId": null,
    "device": null,
    "fulfillmentDeviceId": null,
    "fulfillmentDevice": null,
    "userId": null,
    "locationId": null,
    "location": null,
    "runnerId": null,
    "orderDate": "04/29/2026 10:51 PM",
    "userInfo": {
        "name": "Employee",
        "email": "",
        "phone": "",
        "company": "",
        "booth": "",
        "subscribe": true,
        "dob": "01/01/1901 12:00 AM",
        "customerId": null,
        "ageVerified": false
    },
    "exemptTaxPartIds": null,
    "feeFlat": 0.0,
    "feePercentage": 0.0,
    "feeExists": false,
    "subtotalGross": 0.0,
    "subtotalDeducted": 0.0,
    "subtotalNet": 0.0,
    "discountId": null,
    "discount": null,
    "discountCode": "",
    "discountGross": 0.0,
    "discountDeducted": 0.0,
    "discountNet": 0.0,
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
    "totalGrossMinusTips": 0.0,
    "totalDeducted": 0.0,
    "totalNet": 0.0,
    "note": "",
    "guid": "1721c3d8-c801-475b-831f-02211d5d74e8",
    "saleDate": null,
    "printDate": null,
    "claimedDate": null,
    "lastInboundSmsDate": null,
    "prepDate": null,
    "outDate": null,
    "deliveryDate": null,
    "scheduleDate": null,
    "satisfactionSentDate": null,
    "lastCallSentDate": null,
    "followUpSentDate": null,
    "satisfaction": null,
    "lastDeliveryAttempt": null,
    "deliveryAttempts": 0,
    "tabId": null,
    "posStatus": null,
    "posLastUpdated": null,
    "waiveFees": false,
    "taxExempt": false,
    "priceLevelId": null,
    "options": 0,
    "fulfillmentTimeId": null,
    "posRefId": null,
    "posErrorDetails": null,
    "erpStatus": null,
    "erpRefId": null,
    "erpErrorDetails": null,
    "orderingAppStatus": null,
    "orderingAppRefId": null,
    "orderingAppErrorDetails": null,
    "loyaltyRefId": null,
    "modifyDate": "04/29/2026 10:51 PM",
    "queueId": 0,
    "noItemsRemoved": false,
    "unvoidedItems": [],
    "items": [],
    "modifiersByItem": null,
    "payments": [],
    "loyalty": [],
    "address": {
        "street1": "",
        "street2": "",
        "city": "",
        "state": "",
        "zip": "",
        "country": ""
    },
    "statusList": {
        "admin": 35,
        "mobile": 59,
        "kiosk": 59,
        "orderTaker": 59,
        "hawker": 51,
        "suite": 59,
        "preorder": 59,
        "fulfill": 0,
        "terminal": 35
    },
    "nextStatus": 2,
    "previousStatus": 1,
    "hasRunnerStatus": true,
    "sendToRunner": false,
    "distinctLocations": [],
    "fromSms": "+15555555555",
    "fromEmail": "customer@example.com",
    "discountErrorMessage": null,
    "cultureId": "en-US",
    "notes": {},
    "receiptUrl": "https://storage.tapin2.co/images/example.jpg",
    "taxParts": {},
    "itemTaxParts": {},
    "fees": {},
    "answers": [],
    "containsAlcohol": false,
    "isPaidInFull": true
}
```

## Venue-Specific Notes

- **Sandbox Status**: Active and functional.
- **Payload Size**: The live sandbox returns a valid data payload.

---
[🔗 View Original Documentation](https://api.tapin2.co/Help/Api/GET-v2-venues-venueId-events-eventId-orders-seatId-current)

[← Back to Endpoint Registry](../README.md)
