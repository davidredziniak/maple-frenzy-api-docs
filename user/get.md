# Show info on a user

Get the details of any user given a userId.

**URL** : `/api/user/:userId`

**Method** : `GET`

**Auth required** : YES

**Permissions required** : None for now (Will expand permissions on information limiting)

## Success Response

**Code** : `200 OK`

**Content examples**

For a User with ID 3 on the database.

```json
{
    "id": 3,
    "username": "maplefrenzy_david",
    "createdAt": "2024-03-13T19:49:26.483Z",
    "lastLoggedIn": "2024-03-13T19:49:26.483Z"
}
```

## Error Response

**Code** : `404 NOT FOUND`

**Content example**

```json
{
    "error": "User not found."
}
```
