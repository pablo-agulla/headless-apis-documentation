---
mainPage: true
title: Initial Navigation to obtain URLs
description: Initial Navigation to obtain URLs with Liferay Headless APIs
weight: 6
---

URLs are not part of this API, they may change at any moment. URLs must be asked to the service before making any request.

The URLs can be obtained making a request to `/o/apio`.

Different [hypermedia formats](/docs/general/hypermedia-types.html) are supported for the response.

The response in `json HAL` format will contain a `_links` object with the different links to be used. For example: 

```json
{
    "_links": {
        "self": {
            "href": "http://localhost:8080/o/api"
        },
        "user-account": {
            "href": "http://localhost:8080/o/api/p/user-account"
        },
        "content-space": {
            "href": "http://localhost:8080/o/api/p/content-space"
        },
        "my-user-account": {
            "href": "http://localhost:8080/o/api/p/my-user-account"
        },
        "web-site": {
            "href": "http://localhost:8080/o/api/p/web-site"
        },
        "organization": {
            "href": "http://localhost:8080/o/api/p/organization"
        },
        "roles": {
            "href": "http://localhost:8080/o/api/p/roles"
        }
    }
}
```

The template URLs for managing collections such as Organization or Roles can be
found inside the section `_links` with the keys `organization` or `roles`.
(These keys are our API and they will never change). 

These URLs allow us to build URLs that can always be used to obtain the entities (`GET` method).

Navigating through a collection of entities, the link to each entity can be found with the rel `self`. 