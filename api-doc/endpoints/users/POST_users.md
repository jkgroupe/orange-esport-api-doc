# User Resources

`POST /api/users.{_format}`

## Description
Create a new user.

***

## Requires authentication
None

## Parameters
- **email** _(required)_ - E-mail address 
- **username** _(required)_ - Username 
- **password[password]** _(required)_ - Password
- **password[confirm]** _(required)_ - Password confirmation

## Return format
- **201 Created** — User is created.

## Errors
All known errors cause the resource to return HTTP error code header together with a JSON array containing 
at least 'code' and 'message' keys describing the source of error.

- **400 Bad Request** — The request issued is missing one or more of the required parameters or contains parameters in an invalid form.