# User Resources

`GET /api/users.{_format}`

## Description
Returns the profile information for the current user.

***

## Requires authentication
* A valid JWT token must be provided in **Authorization Bearer** header.

## Parameters
None

## Return format
A JSON object with the following keys and values:
- **username** — Username
- **registration_at** — Registration date of the user

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
/api/users
```

**Return**
``` json
{
  "first_name": "Rush",
  "last_name": "eSport",
  "email": "test@domain.ext",
  "username": "rushesport",
  "address": "Exemple de rue",
  "zipcode": "75001",
  "city": "Paris",
  "phone_number": "+33100000000",
  "accept_newsletter": false,
  "groups": [
    {
      "name": "Default"
    }
  ],
  "last_login": "2016-09-06T12:06:15+0200",
  "registration_at": null
}
```