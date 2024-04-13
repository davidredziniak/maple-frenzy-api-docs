# Signup

Used to sign up a new User.

**URL** : `/api/signup/`

**Method** : `POST`

**Auth required** : NO

**Data constraints**

```json
{
    "username": "[valid unique username]",
    "email": "[valid unique email]",
    "password": "[password in plain text][minimum 8 chars]"
}
```

**Data example**

```json
{
    "username": "maplefrenzyadmin",
    "email": "mappplee@gmail.com",
    "password": "maplefrenzy333!"
}
```

## Success Response

**Code** : `200 OK`

**Content**

```json
{
    "message": "Successfully signed up. Please verify account by clicking the link in the email."
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

If 'email' is already taken.

```json
{
    "error": "Email already taken."
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