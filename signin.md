# Signin

Used to sign in a registered User.

**URL** : `/api/signin/`

**Method** : `POST`

**Auth required** : NO

**Data constraints**

```json
{
    "username": "[valid username]",
    "password": "[password in plain text][minimum 8 chars]"
}
```

**Data example**

```json
{
    "username": "maplefrenzyadmin",
    "password": "maplefrenzy333!"
}
```

## Success Response

**Code** : `200 OK`

**Content**

```json
{
    "accessToken": "93144b288eb1fdccbe46d6fc0f241a51766ecd3d",
    "message": "Successfully signed in."
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

If 'username' does not exist in the database.

```json
{
    "message": "Username not found."
}
```

If 'password' is incorrect for a given username.

```json
{
    "message": "Password incorrect."
}
```