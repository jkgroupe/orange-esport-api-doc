# User Resources

`GET /api/users/:username.{_format}`

## Description
Returns the profile information for a specified user with its username.

***

## Requires authentication
* A valid JWT token must be provided in **Authorization Bearer** header.

## Return format
A JSON object with the following keys and values:
- **username** — Username
- **registration_at** — Registration date of the user

## Parameters
None

## Errors
All known errors cause the resource to return HTTP error code header together with a JSON array containing 
at least 'code' and 'message' keys describing the source of error.

- **400 Bad Request** — Request did not contain one of the required parameters.
- **401 Unauthorized** — Request did not contain a valid JWT token.
- **403 Forbidden** — The user requested has been disabled.
- **404 Not Found** — User does not exist in database.

***
## Example
**Request**
```
/api/users/rushesport
```

**Return**
``` json
{
  "username": "rushesport",
  "registration_at": "2016-09-06T11:35:56+0200"
}
```