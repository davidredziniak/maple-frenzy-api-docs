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
    "accessToken": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6MSwiaWF0IjoxNzEyODYwNjMzLCJleHAiOjE3MTI4NjA5MzN9.afv83XOb2bcqzW9ZCZT8WXSc8EoFQuyORmbi3W9t9pU",
    "refreshToken": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6MSwiaWF0IjoxNzEyODYwNjMzLCJleHAiOjE3MTI4NjQyMzN9.PXRMh-QpUBCldUN2I4ZxHvjb4XsHbtxAoLLOS_Jwui0",
    "message": "Successfully signed up."
}
```

## Error Response

**Code** : `401 UNAUTHORIZED`

**Content examples** :

If 'username' is already taken.

```json
{
    "error": "Username already taken."
}
```

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