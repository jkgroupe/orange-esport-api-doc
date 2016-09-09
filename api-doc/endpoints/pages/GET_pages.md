# Page Resources

`GET /api/pages.{_format}`

## Description
Returns a list of the pages.

***

## Requires authentication
* A valid JWT token must be provided in **Authorization Bearer** header.

## Parameters
- **page** — Return a specific page.
- **per_page** — The number of results to return. Can not be over 100, default 10.
- **sort** — Sort photos in the specified order. Default value: 'published_at'.
    - 'published_at' — Sort by date of publication
    - 'title' — Sort by title
- **direction** — Control the order of the sorting. Default value: 'desc'.
    - 'asc' — Sort in ascending order
    - 'desc' — Sort in descending order.
- **category** — Filter by category's slug.

## Return format
An array with the following keys and values:
- **per_page** — Return the number of items per page.
- **total** — Return the number of items.
- **current_page** — Return the number of the current page. 
- **total_page** — Return the number of pages.
- **pages** — Return an array of page objects.

## Errors
- **400 Bad Request** — Request did not contain one of the required parameters.
- **401 Unauthorized** — Request did not contain a valid JWT token.
- **403 Forbidden** — The page requested has been disabled or does not have access.
- **404 Not Found** — No pages found in database.

## Example
**Request**
```
/api/pages?page=1&per_page=1&sort=title&direction=desc
```

**Return**
``` json
{
  "per_page": 1,
  "total": 4,
  "current_page": 1,
  "total_page": 4,
  "pages": [
    {
      "title": "Mentions légales",
      "slug": "mentions-legales",
      "permalink": "https://www.rushesport.com/mentions-legales",
      "category": {
        "title": "Pied de page",
        "slug": "footer"
      },
      "content": "<p style=\"text-align: center;\">Example of content</p>",
      "published_at": "2016-05-06T02:43:00+0200"
    }
  ]
}
```