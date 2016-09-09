# JWT authentication

`POST /api/auth`

## Description
Allows a user to obtain a JWT token. 
The method will use the currently logged in user as the account for access authorization.

## Parameters
- **username** — Username or e-mail address of the user.
- **password** — Password of the user.

## Return format
The request will contain a token:
- **token** — Return the JWT token.

## Errors
- **401 Unauthorized** — Bad credentials