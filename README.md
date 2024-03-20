# maple-frenzy-api-docs
Documentation on Maple-Frenzy API endpoints
These endpoints will be frequently updated as development progresses.

Current URL:
https://maple-frenzy.onrender.com/

## Open Endpoints

Open endpoints require no Authentication.
The `x-access-token` header is not required.

* [SignIn](signin.md) : `POST /api/signin/`
* [SignUp](signup.md) : `POST /api/signup/`

## Endpoints that require Authentication

Closed endpoints require a valid token to authenticate a request. The `x-access-token` header is required with a valid token that is encrypted with a valid userId. A token can be retrieved in the body of the signin and signup response above.

### User

* [Show info](user/get.md) : `GET /api/user/:userId`

### Trade

Endpoints for viewing and manipulating trades that the Authenticated User has permissions to access.

* [Create a trade](trade/create.md) : `POST /api/trade/create`
* [Delete a trade](trade/delete.md) : `POST /api/trade/delete`
* [Join a trade](trade/join.md) : `POST /api/trade/join`
* [Leave a trade](trade/leave.md) : `POST /api/trade/leave`
* [View trade info](trade/data.md) : `GET /api/trade/data/:tradeId`
