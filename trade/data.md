# Show info on a user

Get the details of any trade given the `tradeId`

**URL** : `/api/trade/data/:tradeId`

**Method** : `GET`

**Auth required** : YES

**Permissions required** : None for now (Will expand permissions on information limiting)

## Success Response

**Code** : `200 OK`

**Content examples**

For a Trade with ID 2 on the database.

```json
{
    "id": 2,
    "sellerId": 4,
    "timeStart": "2024-03-20T16:48:07.930Z",
    "timeEnd": "2024-03-20T16:48:07.930Z",
    "price": 6,
    "region": "lol",
    "buyerLimit": 4,
    "buyerAvailable": 4
}
```

## Error Response

**Code** : `404 NOT FOUND`

**Content example**

```json
{
    "error": "Trade not found."
}
```
