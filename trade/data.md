# View Trade Details

Get the details of any trade given the `tradeId`

**URL** : `/api/trade/data/:tradeId`

**Method** : `GET`

**Auth required** : YES

**Permissions required** : Available for all authenticated users. If the `slots` query is given in the URL, it is limited to the owner of the trade.

## Success Response

**Code** : `200 OK`

**Content examples**

For a Trade with ID 2 on the database.

URL: `/api/trade/data/2`

```json
{
    "id": 2,
    "sellerId": 4,
    "timeStart": "2024-03-20T16:48:07.930Z",
    "timeEnd": "2024-03-22T19:48:07.930Z",
    "price": 6,
    "channels": [1,2,3,4,5,6,7,8,9,10,11],
    "buyerLimit": 4,
    "buyerAvailable": 4
}
```

For a Trade with ID 3 on the database, requested with slot data via the `?slots` query

Positions are provided IN ORDER.

URL: `/api/trade/data/3?slots`

```json
{
    "id": 3,
    "sellerId": 1,
    "timeStart": "2024-03-22T16:22:02.213Z",
    "timeEnd": "2024-03-22T19:22:02.213Z",
    "price": 300,
    "channels": [1,2,3,4,5,6,7,8,9,10,11],
    "buyerLimit": 10,
    "buyerAvailable": 7,
    "slots": [
        {
            "position": 1,
            "userId": 1,
            "channel": 3,
            "duration": 1,
        },
        {
            "position": 2,
            "userId": 3,
            "channel": 1,
            "duration": 3,
        },
        {
            "position": 3,
            "userId": 2,
            "channel": 11,
            "duration": 1,
        }
    ]
}
```

## Error Response

**Code** : `404 NOT FOUND`

**Content**

```json
{
    "error": "Trade not found."
}
```

**Code** : `401 UNAUTHORIZED`

**Content**

If the user is requesting slot data for a trade they don't own.

```json
{
    "error": "You are not authorized to view the slots of this trade."
}
```