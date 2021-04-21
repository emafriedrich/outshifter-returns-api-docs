---
title: API return reference

language_tabs: # must be one of https://git.io/vQNgJ
  - javascript

toc_footers:
  - <a href='https://github.com/slatedocs/slate'>Documentation Powered by Slate</a>

search: true

code_clipboard: true
---

# Returns api


## Base api path
```
qa: https://api-qa-returns.outshifter.com

```

## Add a return

This endpoint create a return

### HTTP Request

`POST api/returns`

### Params =>


```json
{
    "orderId": "1",
    "email": "email@domain.com",
    "date": "2021-04-07T13:56:09.000Z",
    "iban": "NL40INGB9130582334",
    "bic": "NORWNOK1",
    "fullname": "Fullname",
    "items": [
        {
            "id": 1,
            "quantity": 1,
            "itemName": "an product",
            "itemProductId": 1,
            "returnReasonId": 1
        }
    ]
}
```

## Get return reasons

### HTTP Request

`GET api/return-reasons`

> Response

```json
[
  { "id": 1, "reason": "The Product Didn't Match Its Description" },
  { "id": 2, "reason": "I Bought the Wrong Item" },
  { "id": 3, "reason": "The Brand Shipped the Wrong Item" },
  { "id": 4, "reason": "The Product Was Damaged Upon Arrival" },
  { "id": 5, "reason": "Product did not fit" },
  { "id": 6, "reason": "Other" }
]

```

## Get return declined reasons

### HTTP Request

`GET api/return-declined-reasons`

> Response

```json
[
  { "id": 1, "reason": "Wrong products", "needDetail": false },
  { "id": 2, "reason": "Missing items", "needDetail": false },
  {
    "id": 3,
    "reason": "Products looks like it has been used",
    "needDetail": false
  },
  { "id": 4, "reason": "Products were dirty", "needDetail": false },
  { "id": 5, "reason": "Product is made to measure", "needDetail": false },
  { "id": 6, "reason": "Packaging was unsealed", "needDetail": false },
  {
    "id": 7,
    "reason": "Original labels (hang tags) were not attached",
    "needDetail": false
  },
  {
    "id": 8,
    "reason": "Product was not in original packaging",
    "needDetail": false
  },
  {
    "id": 9,
    "reason": "Product was not in original packaging",
    "needDetail": false
  },
    {
    "id": 10,
    "reason": "Others",
    "needDetail": true
  }
]


```
## Get order

### HTTP Request

`GET /api/orders/:orderId`

### URL Parameters

| Parameter | Description  |
| --------- | ------------ |
| orderId   | The order ID |

> Response

```json
{
  "createdAt": "2020-09-08T18:06:48.973Z",
  "updatedAt": "2020-09-08T18:06:48.973Z",
  "id": 12,
  "channel": "Shopify",
  "channelId": "",
  "channelOrderName": "#1079",
  "channelCreatedDate": "2020-09-08T18:06:46.000Z",
  "shippingPrice": "128.00",
  "shippingTitle": "Flate rate price",
  "shippingCode": "Flate rate price",
  "customer": {
    "fullName": "Maximiliano Caba",
    "email": "elmassi22@gmail.com",
    "phone": null,
    "shippingZip": "1439",
    "shippingAddress": "Av Castañares",
    "shippingCity": "Capital",
    "shippingState": null,
    "shippingCountry": "FR",
    "shippingContactName": "Caba",
    "billingName": "Maximiliano Caba",
    "billingZip": "1439",
    "billingCity": "Capital",
    "billingState": null,
    "billingAddress": "Av Castañares",
    "billingCountry": "FR"
  },
  "items": [],
  "reseller": {
    "createdAt": "2020-08-19T18:27:37.804Z",
    "updatedAt": "2020-12-04T19:10:21.000Z",
    "id": 46,
    "deletedAt": null,
    "isBusiness": true,
    "uid": "05kh09mob6XPmZAfihQG0Ve7PQy2",
    "active": true,
    "isAdmin": true,
    "isSupplier": true,
    "username": "maxicaba",
    "name": "Maximiliano",
    "surname": "Caba",
    "dateBirth": "1990-01-01",
    "phone": "9127641924",
    "phoneCode": "",
    "address": "Av rivadavia",
    "address2": null,
    "postCode": "1234",
    "state": "Paris",
    "country": "FR",
    "city": "Lugano",
    "avatar": "https://s3.eu-central-1.amazonaws.com/app.outshifter.com/assets/img/avatar.png",
    "website": "https://",
    "description": "",
    "facebookAccessToken": null,
    "facebookPageId": null,
    "instagramAccountId": null,
    "mangopayId": "86138279",
    "squarespaceApiToken": null,
    "firstSquarespaceImport": false,
    "interests": "",
    "gender": "",
    "contactName": "Maxi",
    "brandName": "mitienda",
    "organizationNumber": "1",
    "vatNumber": "124124",
    "warehouseSameAddress": true,
    "termsAndConditions": false,
    "privacyPolicy": false,
    "coverImage": null,
    "rate": 0,
    "shopifyAccessToken": null,
    "shopifyExportAccessToken": null,
    "shopifyUrl": null,
    "shopifyCurrency": null,
    "shopifyCarrierId": null,
    "shopifyFulfillmentId": null,
    "shopifyLocationId": null,
    "business2": {
      "sameAsAccount": false,
      "businessName": null,
      "country": null,
      "address": null,
      "address2": null,
      "postCode": null,
      "city": null,
      "ecommerceSystem": null,
      "products": {
        "category": null,
        "subcategory": null,
        "commission": null,
        "channels": null
      },
      "contact": {
        "title": null,
        "name": null,
        "surname": null,
        "email": null,
        "role": null,
        "phoneCode": null,
        "phone": null
      },
      "return": {
        "right": null,
        "label": null,
        "cost": null,
        "policy": null,
        "address": {
          "sameAsBusiness": false,
          "sameAsWarehouse": false,
          "country": null,
          "timezone": null,
          "address": null,
          "address2": null,
          "postCode": null,
          "returnCity": null
        }
      },
      "fulfillment": {
        "shippingRates": null,
        "processingTime": null,
        "shippingTo": null
      }
    },
    "warehouse": {
      "address": "Av rivadavia",
      "address2": null,
      "postCode": "1234",
      "state": "Paris",
      "country": "FR",
      "timezone": "Europe/Paris",
      "city": "Lugano"
    },
    "check": {
      "firstSyncShopify": false,
      "firstSyncWoo": false,
      "activateGuide": false
    }
  },
  "trackings": []
}
```

## Test order exists

Test if order exists

### HTTP Request

`GET /api/orders/testOder/:orderId`

### URL Parameters

| Parameter | Description  |
| --------- | ------------ |
| orderId   | The order Id to test if order exists |


> Response

```json
{"exists":true}
```

## Test customer email exists

### HTTP Request

`GET /api/orders/testEmail/:email`

### URL Parameters

| Parameter | Description  |
| --------- | ------------ |
| email   | a valid email |


> Response

```json
{"exists":true}
```

# Outshifter main api

```
qa: https://api-qa.outshifter.com
pro: https://api.outshifter.com

```

## Set return status

### HTTP Request

`POST /api/returns/setReturnStatus`

<aside class="warning"> Note that the returnDeclinedReasonDetails is need only if the returnDeclinedReason need detail (like "others") </aside>

> Send JSON object like this

```json
{
    "itemId": 1,
    "returnStatus": "DECLINED",
    "returnDeclinedReasonId": 1,
    "returnDeclinedReasonDetail": "El producto estaba roto"
}
```

> or this

```json
{
    "itemId": 1,
    "returnStatus": "APPROVED"
}
```
