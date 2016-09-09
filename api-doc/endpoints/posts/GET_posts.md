# Post Resources

`GET /api/posts.{_format}`

## Description
Returns a list of the posts.

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
- **posts** — Return an array of post objects.

## Errors
- **400 Bad Request** — Request did not contain one of the required parameters.
- **401 Unauthorized** — Request did not contain a valid JWT token.
- **403 Forbidden** — The page requested has been disabled or does not have access.
- **404 Not Found** — No posts found in database.

## Example
**Request**
```
/api/posts?page=1&per_page=1&sort=title&direction=desc
```

**Return**
``` json
{
  "per_page": 1,
  "total": 16,
  "current_page": 1,
  "total_page": 16,
  "posts": [
    {
      "title": "Revivez la Masterclass Deus Ex avec Jonathan Jacques-Belletête !",
      "permalink": "https://www.rushesport.com/a-la-une/revivez-la-masterclass-deus-ex-avec-jonathan-jacques-belletete",
      "excerpt": "Le mercredi 06 Juillet dernier, deux Rushers ont eu l'honneur d'assister en VIP à la Masterclass Deus Ex, organisée par Jeux Vidéo Magazine, la Cité des Sciences et de l’Industrie en partenariat avec Orange. Aujourd'hui, nous vous proposons de vivre ou revivre cette soirée qui a placé Jonathan Jacques-Belletête sous les projecteurs.",
      "category": {
        "title": "À la une",
        "slug": "a-la-une"
      },
      "cover": {
        "name": "tim.jpg",
        "url": "https://www.rushesport.com/uploads/images/8416db2986dce29c89777c77037a284b9d2d66eb.jpeg"
      },
      "content": "<p style=\"text-align: center;\">Example of content</p>",
      "published_at": "2016-08-01T12:12:00+0200"
    }
  ]
}
```