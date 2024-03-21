# Show info on a user

Get the details of any user given a userId.

**URL** : `/api/user/:userId`

**Method** : `GET`

**Auth required** : YES

**Permissions required** : None for now (Will expand permissions on information limiting)

## Success Response

**Code** : `200 OK`

**Content**

For a User with ID 3 on the database.

```json
{
    "id": 3,
    "username": "maplefrenzy_admin",
    "tradeCount": 0,
    "reputation": 0,
    "createdAt": "2024-03-21T16:17:21.768Z",
    "lastLoggedIn": "2024-03-21T16:17:21.768Z"
}
```

## Error Response

**Code** : `404 NOT FOUND`

**Content examples**

Invalid userId provided in the request.

```json
{
    "error": "User not found."
}
```

The userId provided was valid, but for some reason there is no user profile attached to it.

```json
{
    "error": "User profile not found."
}
```