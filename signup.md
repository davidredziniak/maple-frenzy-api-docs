# Signup

Used to sign up a new User.

**URL** : `/api/signup/`

**Method** : `POST`

**Auth required** : NO

**Data constraints**

```json
{
    "username": "[valid username]",
    "password": "[password in plain text]"
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

**Content example**

```json
{
    "accessToken": "93144b288eb1fdccbe46d6fc0f241a51766ecd3d",
    "message": "Successfully signed up."
}
```

## Error Response

**Condition** : All errors

**Code** : `500 INTERNAL SERVER ERROR`

**Content** :

```json
{
    "error": "Server error with details"
}
```