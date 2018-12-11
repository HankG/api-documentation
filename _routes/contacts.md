---
title: Contacts
see_also:
  - aspects
---

{% include toc.md %}

## Get list of contacts in an aspect

### Request

~~~
GET /api/v1/aspects/:aspect_id/contacts
~~~

### Response

~~~json
[
  {
    "guid": "f50ffc00b188013355e3705681972339",
    "diaspora_id": "alice@example.com",
    "name": "Alice Testing",
    "avatar": "http://example.com/uploads/images/thumb_medium_83abe5319ef830c2bd84.jpg"
  },
  {
    "guid": "cb7e4aa0b82f0133e40d406c8f31e210",
    "diaspora_id": "bob@example.com",
    "name": "Bob Testing",
    "avatar": "http://example.com/uploads/images/thumb_medium_a51bf501fe86c198c0b1.jpg"
  }
]
~~~

### Errors

| Status code | Error reason                               |
| ----------- | ------------------------------------------ |
| 404         | Aspect with provided ID could not be found |


## Add a user to an aspect

### Request

~~~
POST /api/v1/aspects/:aspect_id/contacts
~~~
~~~json
{
  "person_guid": "f50ffc00b188013355e3705681972339"
}
~~~

### Response

~~~
Status: 204 No Content
~~~

### Errors

| Status code | Error reason                               |
| ----------- | ------------------------------------------ |
| 404         | Aspect with provided ID could not be found |
| 422         | Failed to add user to aspect               |


## Remove a user from an aspect

### Request

~~~
DELETE /api/v1/aspects/:aspect_id/contacts/:person_guid
~~~

### Response

~~~
Status: 204 No Content
~~~

### Errors

| Status code | Error reason                               |
| ----------- | ------------------------------------------ |
| 404         | Aspect with provided ID could not be found |
| 422         | Failed to remove user from aspect          |

[aspects]: {{ site.baseurl }}/routes/aspects.html
