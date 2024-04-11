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
    "accessToken": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6MSwiaWF0IjoxNzEyODYwNjM3LCJleHAiOjE3MTI4NjA5Mzd9.ubcK8_oWF_fKFg1iiNP01cDzOtvaC0Zpx1qkajNvAWA",
    "refreshToken": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6MSwiaWF0IjoxNzEyODYwNjM3LCJleHAiOjE3MTI4NjQyMzd9._1YsYCUDSTmsLtCxArB9z6tYYnIEn170ZUTXo58clAc",
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