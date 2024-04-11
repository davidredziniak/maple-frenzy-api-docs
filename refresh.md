# Refresh

Need to be called as soon as the current accessToken is going to expire.
Used to gain a new accessToken and refreshToken to persist user login.

**URL** : `/api/refresh/`

**Method** : `POST`

**Auth required** : NO

**Data constraints**

```json
{
    "userId": "[valid userId in integer form]",
    "refreshToken": "[the stored refreshToken from previous login/refresh]"
}
```

**Data example**

```json
{
    "userId": 1,
    "refreshToken": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6MSwiaWF0IjoxNzEyODYwMTIwLCJleHAiOjE3MTI4NjA0MjB9.EXVYOyX7NZlU1AA_c2_XpE2sfw95h2yOzVxc1VAERcg"
}
```

## Success Response

**Code** : `200 OK`

**Content**

```json
{
    "accessToken": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6MSwiaWF0IjoxNzEyODYwMTIwLCJleHAiOjE3MTI4NjA0MjB9.EXVYOyX7NZlU1AA_c2_XpE2sfw95h2yOzVxc1VAERcg",
    "refreshToken": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6MSwiaWF0IjoxNzEyODYwMTIwLCJleHAiOjE3MTI4NjM3MjB9.sFGejO7SlTKaVH4RHLkN8Te_HOpvw8-EezqOeNg-Y2E",
    "message": "Successfully refreshed tokens."
}
```

## Error Response

**Code** : `401 UNAUTHORIZED`

**Content examples**


If 'refreshToken' is valid but does not match the userId.

```json
{
    "message": "Invalid token provided. Please sign in again."
}
```

If the 'refreshToken' has expired already. Need to sign in again.

```json
{
    "message": "Invalid token provided. Please sign in again."
}
```
