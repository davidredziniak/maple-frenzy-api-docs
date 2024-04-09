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

**Content examples**

The requested timeStart and timeEnd are either the same time, or the timeStart comes after timeEnd

```json
{
    "error": "Trade startTime and endTime are invalid."
}
```

The requested timeStart and timeEnd are valid, but the time difference is not in intervals of an hour (ex. duration is 1.5 hours)

```json
{
    "error": "The requested trade times have to be in intervals of an hour."
}
```

The list of channels available by the seller is invalid (is not an array of strictly integers)

```json
{
    "error": "The list of channels requested are invalid."
}
```

**Condition** : All other errors

**Code** : `400 BAD REQUEST`

**Content** :

```json
{
    "error": "Server error with details"
}
```