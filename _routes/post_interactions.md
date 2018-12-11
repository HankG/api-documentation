---
title: Post interactions
see_also:
  - comments
  - likes
  - reshares
---

{% include toc.md %}

## Report a post

### Request

~~~
POST /api/v1/posts/:post_guid/report
~~~
~~~json
{
  "reason": "Using my images without my permission."
}
~~~

### Response

~~~
Status: 204 No Content
~~~

### Errors

| Status code | Error reason                               |
| ----------- | ------------------------------------------ |
| 404         | Post with provided guid could not be found |
| 422         | Failed to create report on this post       |

## Subscribe to a post

The current user will receive notifications for subscribed posts without adding a like or comment.

### Request

~~~
POST /api/v1/posts/:post_guid/subscribe
~~~

### Response

~~~
Status: 204 No Content
~~~

### Errors

| Status code | Error reason                               |
| ----------- | ------------------------------------------ |
| 404         | Post with provided guid could not be found |
| 422         | Can't subscribe to this post               |

## Mute a post

The current user will not receive any notifications for this post, even if a comment or like was added.

### Request

~~~
POST /api/v1/posts/:post_guid/mute
~~~

### Response

~~~
Status: 204 No Content
~~~

### Errors

| Status code | Error reason                               |
| ----------- | ------------------------------------------ |
| 404         | Post with provided guid could not be found |

## Hide a post

Toggles whether a given post will be excluded from all streams and search results.

### Request

~~~
POST /api/v1/posts/:post_guid/hide
~~~

### Response

~~~
Status: 204 No Content
~~~

### Errors

| Status code | Error reason                               |
| ----------- | ------------------------------------------ |
| 404         | Post with provided guid could not be found |

[comments]: {{ site.baseurl }}/routes/comments.html
[likes]: {{ site.baseurl }}/routes/likes.html
[reshares]: {{ site.baseurl }}/routes/reshares.html
