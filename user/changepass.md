# Change a Users Password

Modify the user password

**URL** : `/api/user/changepass`

**Method** : `POST`

**Auth required** : YES

**Data constraints**

```json
{
    "password": "[valid password in plain text]",
    "newPassword": "[password in plain text][minimum 8 chars]"
}
```

**Data example**

```json
{
    "password": "imapassword12",
    "newPassword": "wownewpassword1"
}
```

## Success Response

**Code** : `200 OK`

**Content**

For a User current password `imapassword` and a new password `12345678`

```json
{
    "message": "Successfully updated password!"
}
```

## Error Response

**Code** : `401 UNAUTHORIZED`

**Content examples**

If 'password' is less than 8 characters.

```json
{
    "message": "Password provided was invalid."
}
```

If the current password in the request body does not match the database.

```json
{
    "message": "Current password provided is incorrect."
}
```

**Code** : `404 NOT FOUND`

**Content**

Invalid userId provided in the `x-access-token` header.

```json
{
    "error": "User not found."
}
```