# View Trade Details

Get the full list of trades available in the database.

**URL** : `/api/trade/list`

**Method** : `GET`

**Auth required** : YES

## Success Response

**Code** : `200 OK`

**Content examples**

A list of trades exists.

```json
{
    "trades": [
        {
            "id": 1,
            "sellerId": 1,
            "price": 300,
            "channels": [3,4,5,6,7,10,11],
            "timeStart": "2024-03-22T16:22:02.213Z",
            "timeEnd": "2024-03-22T18:22:02.213Z",
            "buyerLimit": 10,
            "buyerAvailable": 10
        },
        {
            "id": 2,
            "sellerId": 2,
            "price": 600,
            "channels": [4,5,6,7,8],
            "timeStart": "2024-03-22T16:23:22.735Z",
            "timeEnd": "2024-03-22T18:23:22.736Z",
            "buyerLimit": 15,
            "buyerAvailable": 5
        }
    ]
}
```

There are no trades in the database.

```json
{
    "trades": []
}
```

## Error Response

**Code** : `400 BAD REQUEST`

**Condition** : All errors

**Content**

```json
{
    "error": "Server error with details"
}
```