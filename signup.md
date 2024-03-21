# Signup

Used to sign up a new User.

**URL** : `/api/signup/`

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
    "message": "Successfully signed up."
}
```

## Error Response

**Code** : `400 BAD REQUEST`

**Content** :

If 'username' is already taken.

```json
{
    "error": "Username already taken."
}
```

**Code** : `401 UNAUTHORIZED`

**Content** :

If 'password' is less than 8 characters.

```json
{
    "message": "Password provided was invalid."
}
```

**Condition** : All other errors

**Code** : `500 INTERNAL SERVER ERROR`

**Content** :

```json
{
    "error": "Server error with details"
}
```