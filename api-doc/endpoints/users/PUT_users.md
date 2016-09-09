# User Resources

`PUT /api/users/:username.{_format}`

## Description
Updates the current user's profile.

***

## Requires authentication
* A valid JWT token must be provided in **Authorization Bearer** header.

## Parameters
- **firstName** _(required)_ - First name of the user 
- **lastName** _(required)_ - Last name of the user 
- **email** _(required)_ - E-mail address of the user  
- **newsletter** _(required)_ - The user accept to receive newsletter
- **address** _(required)_ - Address of the user 
- **zipcode** _(required)_ - Zipcode of the user  
- **city** _(required)_ - City of the user  
- **phoneNumber** _(required)_ - Phone number of the user
- **password[password]** - Password of the user 
- **password[confirm]** - Password confirmation

## Return format
- **204 No Content** — User's profile is updated.

## Errors
All known errors cause the resource to return HTTP error code header together with a JSON array containing 
at least 'code' and 'message' keys describing the source of error.

- **400 Bad Request** — The request issued is missing one or more of the required parameters or contains parameters in an invalid form.
- **401 Unauthorized** — Request did not contain a valid JWT token.
- **403 Forbidden** — The user requested has been disabled.
- **404 Not Found** — User does not exist in database.