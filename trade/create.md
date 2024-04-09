# Create a Trade

Create a new trade.

**URL** : `/api/trade/create`

**Method** : `POST`

**Auth required** : YES

**Data constraints**

```json
{
    "price": "[valid price in integer form]",
    "startTime": "[valid start time in ISO format]",
    "endTime": "[valid start time in ISO format]",
    "channels": "[channels in an array of integers]",
    "buyerLimit": "[valid buyer limit in integer form]"
}
```

**Data example**

```json
{
    "price": 1000,
    "timeStart": "2024-03-22T16:22:02.213Z",
    "timeEnd": "2024-03-22T19:22:02.213Z",
    "channels": [1,2,3,4,5,6,7],
    "buyerLimit": 15
}
```

## Success Response

**Code** : `200 OK`

**Content**

Create a trade with a price of 1000 for a duration of 3 hours that exists in channels 1 through 7, limited to 15 buyers.

```json
{
    "id": 3,
    "message": "Successfully created trade."
}
```

## Error Response

**Condition** : All errors

**Code** : `400 Bad Request`

**Content** :

```json
{
    "error": "Server error with details"
}
```