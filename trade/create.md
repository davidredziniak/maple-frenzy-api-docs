# Create a Trade

Create a new trade.

**URL** : `/api/trade/create`

**Method** : `POST`

**Auth required** : YES

**Data constraints**

```json
{
    "price": "[valid price in integer form]",
    "region": "[region]",
    "buyerLimit": "[valid buyer limit in integer form]"
}
```

**Data example**

```json
{
    "price": 1000,
    "region": "Global",
    "buyerLimit": 15
}
```

## Success Response

**Code** : `200 OK`

**Content**

Create a trade with a price of 1000 in the Global region limited to 15 buyers.

```json
{
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

## Notes
Currently the `timeStart` and `timeEnd` fields in the required request body are non functional (for development reasons). 