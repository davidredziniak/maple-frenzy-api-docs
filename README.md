# maple-frenzy-api-docs
Documentation on Maple-Frenzy API endpoints
These endpoints will be frequently updated as development progresses.

Current URL:
https://api.maplefrenzy.com

## Open Endpoints

Open endpoints require no Authentication.
The `x-access-token` header is not required.

* [SignIn](signin.md) : `POST /api/signin/`
* [SignUp](signup.md) : `POST /api/signup/`
* [Refresh](refresh.md) : `POST /api/refresh/`

## Endpoints that require Authentication

Closed endpoints require a valid token to authenticate a request. The `x-access-token` header is required with a valid token that is encrypted with a valid userId. A token can be retrieved in the body of the signin and signup response above.

The `accessToken` is valid for 60 minutes.
The `refreshToken` is valid for 1 day.

### User

* [Show info](user/get.md) : `GET /api/user/:userId`
* [Change password](user/changepass.md) : `POST /api/user/changepass`

### Trade

Endpoints for manipulating trades that the Authenticated User has permissions to access.

* [Create a trade](trade/create.md) : `POST /api/trade/create`
* [Delete a trade](trade/delete.md) : `POST /api/trade/delete`
* [Join a trade](trade/join.md) : `POST /api/trade/join`
* [Leave a trade](trade/leave.md) : `POST /api/trade/leave`

### Trade Data

Endpoints for viewing trade data that the Authenticated User has permissions to access.

* [View list of trades](trade/list.md) : `GET /api/trade/list`
* [View trade details](trade/data.md) : `GET /api/trade/data/:tradeId`
