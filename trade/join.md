# Join a Trade

Join an existing trade.

**URL** : `/api/trade/join`

**Method** : `POST`

**Auth required** : YES

**Data constraints**

```json
{
    "tradeId": "[valid tradeId in integer form]",
    "duration": "[valid number of hours]",
    "channel": "[valid channel in the trade's channel range in integer form]",
}
```

**Data example**

```json
{
    "tradeId": 5,
    "duration": 2,
    "channel": 7,
}
```

## Success Response

**Code** : `200 OK`

**Content**

Join an existing `tradeId` 5 at the channel 5 for 2 hours.

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

If the trade has already started/finished or is ongoing.

```json
{
    "error": "You can't join a trade that is ongoing/completed."
}
```

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

User requests a duration that exceeds the trade time

```json
{
    "error": "Invalid requested duration."
}
```

User requests a channel that is not made available by the seller in the trade

```json
{
    "error": "Invalid requested channel."
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

