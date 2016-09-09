# Page Resources

`GET /api/pages/:slug.{_format}`

## Description
Returns a page with its slug.

***

## Requires authentication
* A valid JWT token must be provided in **Authorization Bearer** header.

## Return format
A JSON object with the following keys and values:
- **title** — Title of the page
- **slug** — Slug of the page
- **permalink** — Permalink of the page
- **category** — Category of the page
- **content** — HTML content of the page 
- **published_at** — Published date of the page

## Errors
- **400 Bad Request** — Request did not contain one of the required parameters.
- **401 Unauthorized** — Request did not contain a valid JWT token.
- **403 Forbidden** — The page requested has been disabled or does not have access.
- **404 Not Found** — Page with the specific slug does not exist.

## Example
**Request**
```
/api/pages/mentions-legales
```

**Return**
``` json
{
  "title": "Mentions légales",
  "slug": "mentions-legales",
  "permalink": "https://www.rushesport.com/mentions-legales",
  "category": {
    "title": "Pied de page",
    "slug": "footer"
  },
  "content": "<p style=\"text-align: center;\">Example of content</p>",
  "published_at": "2016-04-18T20:00:00+0200"
}
```