# Leave a Trade

Leave an existing trade.

**URL** : `/api/trade/leave`

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

Leave an existing `tradeId` 5 that the user has joined.

```json
{
    "message": "Successfully left the trade."
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

If the user has not joined the specific trade.

```json
{
    "error": "You are not in this trade."
}
```

If the user trying to leave a trade is the user that initially created the trade.

```json
{
    "error": "You can't leave a trade that you created."
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

