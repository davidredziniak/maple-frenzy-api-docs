# Join a trade

Join an existing trade.

**URL** : `/api/trade/join`

**Method** : `POST`

**Auth required** : YES

**Data constraints**

```json
{
    "tradeId": "[valid tradeId in integer form]",
}
```

**Data example**

```json
{
    "tradeId": 5,
}
```

## Success Response

**Code** : `200 OK`

**Content**

Join an existing `tradeId` 5.

```json
{
    "message": "Successfully joined the trade."
}
```

## Error Response

**Condition** : The given `tradeID` does not exist.

**Code** : `404 NOT FOUND`

**Content** :

```json
{
    "error": "Trade not found."
}
```

**Code** : `400 BAD REQUEST`

**Content examples**

If the user has already joined the trade.

```json
{
    "error": "You already joined this trade."
}
```

If the trade has already reached its capacity.

```json
{
    "error": "The trade queue is already full."
}
```

If the user trying to join a trade is the user that initially created the trade.

```json
{
    "error": "You can't join a trade that you created."
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

