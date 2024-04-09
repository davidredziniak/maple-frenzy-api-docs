# Delete a Trade

Delete an existing trade.

**URL** : `/api/trade/delete`

**Method** : `POST`

**Auth required** : YES

**Permissions required** : The authorized user token has to match the userID that initially created the trade.

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

Delete a trade with `tradeId` 5.

```json
{
   "message": "Successfully deleted the trade."
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

**Condition** : The authorized user making the request does not match the `userID` that created the trade.

**Code** : `401 UNAUTHORIZED`

**Content** :

```json
{
    "error": "You are unauthorized to delete this trade."
}
```

**Condition** : All errors

**Code** : `400 Bad Request`

**Content examples**

If the trade has already started/finished or is ongoing.

```json
{
    "error": "You can't join a trade that is ongoing/completed."
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