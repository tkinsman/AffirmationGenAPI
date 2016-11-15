---
title: Affirmation Generator API

language_tabs:
  - javascript: JavaScript
  - shell: cURL
  - http: HTTP

toc_footers:
  - <a href='https://github.com/tripit/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true
---

# Introduction

Welcome to the Affirmation API! You can use our API to access Affirmation API endpoints that can send you an affirmation (or affirmations) from different affirmation categories in our database.

We have language bindings in  JavaScript, Shell, and HTTP. You can view code examples in the dark area to the right, and you can switch the programming language of the examples with the tabs in the top right.


This example API documentation page was created with [Slate](https://github.com/tripit/slate).

# Authentication


```javascript

jQuery.ajax({
    url: "http://138.68.48.6:8080/affirmation-project/affirmationservice/affirmations",
    type: "GET",
    headers: {
        "Authorization": "Basic ************==",
        "Content-Type": "multipart/form-data; charset=utf-8; boundary=__X_PAW_BOUNDARY__",
    },
})
.done(function(data, textStatus, jqXHR) {
    console.log("HTTP Request Succeeded: " + jqXHR.status);
    console.log(data);
})
.fail(function(jqXHR, textStatus, errorThrown) {
    console.log("HTTP Request Failed");
})
.always(function() {
    /* ... */
});


```

```shell

curl -X "GET" "http://138.68.48.6:8080/affirmation-project/affirmationservice/affirmations" \
     -H "Content-Type: multipart/form-data; charset=utf-8; boundary=__X_PAW_BOUNDARY__" \
     -u user:password

```

```http

GET /affirmation-project/affirmationservice/affirmations HTTP/1.1
Authorization: Basic ************=
Content-Type: multipart/form-data; charset=utf-8; boundary=__X_PAW_BOUNDARY__
Host: 138.68.48.6:8080
Connection: close
User-Agent: Paw/3.0.12 (Macintosh; OS X/10.11.6) GCDHTTPRequest

```

Affirmation Generator uses basic authentication to allow access to the API with a user name and password. All requests must add the proper authentication to a request for a valid response. You can request a user name and password by emailing the developers. 

### Developer Contact Information

Developer | Email
--------- | -----------
Todd | todd.kinsman@gmail.com
Sandi | sandineedstogivepermission@gmail.com


# Affirmations

## Get All Affirmations


```javascript

jQuery.ajax({
    url: "http://138.68.48.6:8080/affirmation-project/affirmationservice/affirmations",
    type: "GET",
    headers: {
        "Authorization": "Basic ************=",
        "Content-Type": "multipart/form-data; charset=utf-8; boundary=__X_PAW_BOUNDARY__",
    },
})
.done(function(data, textStatus, jqXHR) {
    console.log("HTTP Request Succeeded: " + jqXHR.status);
    console.log(data);
})
.fail(function(jqXHR, textStatus, errorThrown) {
    console.log("HTTP Request Failed");
})
.always(function() {
    /* ... */
});


```

```shell

curl -X "GET" "http://138.68.48.6:8080/affirmation-project/affirmationservice/affirmations" \
     -H "Content-Type: multipart/form-data; charset=utf-8; boundary=__X_PAW_BOUNDARY__" \
     -u user:password

```

```http

GET /affirmation-project/affirmationservice/affirmations HTTP/1.1
Authorization: Basic ************=
Content-Type: multipart/form-data; charset=utf-8; boundary=__X_PAW_BOUNDARY__
Host: 138.68.48.6:8080
Connection: close
User-Agent: Paw/3.0.12 (Macintosh; OS X/10.11.6) GCDHTTPRequest

```

> The above command returns JSON structured like this:

```json
[
  {
    "affirmationId": 3,
    "phrase": "Happiness is my birthright. I embrace happiness as my set point state of being.",
    "rating": 15,
    "categoryId": 1
  },
  {
    "affirmationId": 4,
    "phrase": "I feel joy and contentment in this moment right now.",
    "rating": 2,
    "categoryId": 1
  },
  {
    "affirmationId": 5,
    "phrase": " I awaken in the morning feeling happy and enthusiastic about life.",
    "rating": 2,
    "categoryId": 1
  }, ...
]
```

This endpoint retrieves all Affirmations.

### HTTP Request

`GET http://138.68.48.6:8080/affirmation-project/affirmationservice/affirmations/`

### Response Parameters


[Affirmation Response Parameters](#affirmation-response)
<aside class="success">
A successful response is the best affirmation of all!
</aside>

## Get Affirmation by Category

```javascript

jQuery.ajax({
    url: "http://138.68.48.6:8080/affirmation-project/affirmationservice/affirmations/categories/Happiness",
    type: "GET",
    headers: {
        "Authorization": "Basic dXNlcjoqKioqKiBIaWRkZW4gY3JlZGVudGlhbHMgKioqKio=",
        "Content-Type": "multipart/form-data; charset=utf-8; boundary=__X_PAW_BOUNDARY__",
    },
})
.done(function(data, textStatus, jqXHR) {
    console.log("HTTP Request Succeeded: " + jqXHR.status);
    console.log(data);
})
.fail(function(jqXHR, textStatus, errorThrown) {
    console.log("HTTP Request Failed");
})
.always(function() {
    /* ... */
});

```

```shell

curl -X "GET" "http://138.68.48.6:8080/affirmation-project/affirmationservice/affirmations/categories/Happiness" \
     -H "Content-Type: multipart/form-data; charset=utf-8; boundary=__X_PAW_BOUNDARY__" \
     -u user:***** Hidden credentials *****

```

```http

GET /affirmation-project/affirmationservice/affirmations/categories/Happiness HTTP/1.1
Authorization: ***** Hidden credentials *****
Content-Type: multipart/form-data; charset=utf-8; boundary=__X_PAW_BOUNDARY__
Host: 138.68.48.6:8080
Connection: close
User-Agent: Paw/3.0.12 (Macintosh; OS X/10.11.6) GCDHTTPRequest

```
> The above command returns JSON structured like this:

```json

```

### HTTP Request

`GET http://138.68.48.6:8080/affirmation-project/affirmationservice/affirmations/categories/{category name parameter}`

### URL Parameters

The table lists the {category name parameters} available to generate a valid response. 

Parameter | Type | Description
--------- | ----------- | --------
Happiness | String | The Happiness category of affirmations
Relationships | String | The Relationships category of affirmations
Success | String | The Success category of affirmations
Confidence | String | The Confidence category of affirmations
Self-Esteem | String | The Self-Esteem category of affirmations
Health | String | The Health category of affirmations
Peace | String | The Peace category of affirmations
Mindfulness | String | The Mindfulness category of affirmations
Inner Calm | String | The Inner Calm category of affirmations
NSFW | String | The NSFW category of affirmations. This should be gotten with discretion! No safe for kids

[Affirmation Response Parameters](#affirmation-response)


## Up-vote an Affirmation 

```javascript

jQuery.ajax({
    url: "http://138.68.48.6:8080/affirmation-project/affirmationservice/affirmations/upvote/3",
    type: "PUT",
    headers: {
        "Authorization": "Basic dXNlcjoqKioqKiBIaWRkZW4gY3JlZGVudGlhbHMgKioqKio=",
        "Content-Type": "application/x-www-form-urlencoded; charset=utf-8",
    },
    contentType: "application/x-www-form-urlencoded",
    data: {
    },
})
.done(function(data, textStatus, jqXHR) {
    console.log("HTTP Request Succeeded: " + jqXHR.status);
    console.log(data);
})
.fail(function(jqXHR, textStatus, errorThrown) {
    console.log("HTTP Request Failed");
})
.always(function() {
    /* ... */
});


```

```shell

curl -X "PUT" "http://138.68.48.6:8080/affirmation-project/affirmationservice/affirmations/upvote/3" \
     -H "Content-Type: application/x-www-form-urlencoded; charset=utf-8" \
     -u user:***** Hidden credentials *****

```

```http

PUT /affirmation-project/affirmationservice/affirmations/upvote/3 HTTP/1.1
Authorization: ***** Hidden credentials *****
Content-Type: application/x-www-form-urlencoded; charset=utf-8
Host: 138.68.48.6:8080
Connection: close
User-Agent: Paw/3.0.12 (Macintosh; OS X/10.11.6) GCDHTTPRequest
Content-Length: 0


```

> The above command returns JSON structured like this:

```json

  {
    "affirmationId": 3,
    "phrase": "Happiness is my birthright. I embrace happiness as my set point state of being.",
    "rating": 16,
    "categoryId": 1
  }

```

### HTTP Request

`PUT http://138.68.48.6:8080/affirmation-project/affirmationservice/affirmations/upvote/{affirmationId}`

You must know the id of the affirmation you wish to *upvote* in order to create a valid request.

### URL Parameters

Parameter | Type | Description
--------- | ----------- | --------
affirmationId | int | The id of the affirmation you wish to *upvote*.

[Affirmation Response Parameters](#affirmation-response)

## Down-vote an Affirmation 

```javascript

jQuery.ajax({
    url: "http://138.68.48.6:8080/affirmation-project/affirmationservice/affirmations/downvote/3",
    type: "PUT",
    headers: {
        "Authorization": "Basic dXNlcjoqKioqKiBIaWRkZW4gY3JlZGVudGlhbHMgKioqKio=",
        "Content-Type": "application/x-www-form-urlencoded; charset=utf-8",
    },
    contentType: "application/x-www-form-urlencoded",
    data: {
    },
})
.done(function(data, textStatus, jqXHR) {
    console.log("HTTP Request Succeeded: " + jqXHR.status);
    console.log(data);
})
.fail(function(jqXHR, textStatus, errorThrown) {
    console.log("HTTP Request Failed");
})
.always(function() {
    /* ... */
});


```

```shell

curl -X "PUT" "http://138.68.48.6:8080/affirmation-project/affirmationservice/affirmations/downvote/3" \
     -H "Content-Type: application/x-www-form-urlencoded; charset=utf-8" \
     -u user:***** Hidden credentials *****

```

```http

PUT /affirmation-project/affirmationservice/affirmations/downvote/3 HTTP/1.1
Authorization: ***** Hidden credentials *****
Content-Type: application/x-www-form-urlencoded; charset=utf-8
Host: 138.68.48.6:8080
Connection: close
User-Agent: Paw/3.0.12 (Macintosh; OS X/10.11.6) GCDHTTPRequest
Content-Length: 0

```

> The above command returns JSON structured like this:

```json
 
  {
    "affirmationId": 3,
    "phrase": "Happiness is my birthright. I embrace happiness as my set point state of being.",
    "rating": 15,
    "categoryId": 1
  }

```

### HTTP Request

`PUT http://138.68.48.6:8080/affirmation-project/affirmationservice/affirmations/downvote/{affirmationId}`

You must know the id of the affirmation you wish to *downvote* in order to create a valid request.

### URL Parameters

Parameter | Type | Description
--------- | ----------- | --------
affirmationId | int | The id of the affirmation you wish to *downvote*.

[Affirmation Response Parameters](#affirmation-response)

## Get a Specific Affirmation

```javascript

jQuery.ajax({
    url: "http://138.68.48.6:8080/affirmation-project/affirmationservice/affirmations/4",
    type: "GET",
    headers: {
        "Authorization": "Basic dXNlcjoqKioqKiBIaWRkZW4gY3JlZGVudGlhbHMgKioqKio=",
        "Content-Type": "multipart/form-data; charset=utf-8; boundary=__X_PAW_BOUNDARY__",
    },
})
.done(function(data, textStatus, jqXHR) {
    console.log("HTTP Request Succeeded: " + jqXHR.status);
    console.log(data);
})
.fail(function(jqXHR, textStatus, errorThrown) {
    console.log("HTTP Request Failed");
})
.always(function() {
    /* ... */
});

```

```shell

curl -X "GET" "http://138.68.48.6:8080/affirmation-project/affirmationservice/affirmations/4" \
     -H "Content-Type: multipart/form-data; charset=utf-8; boundary=__X_PAW_BOUNDARY__" \
     -u user:***** Hidden credentials *****

```

```http

GET /affirmation-project/affirmationservice/affirmations/4 HTTP/1.1
Authorization: ***** Hidden credentials *****
Content-Type: multipart/form-data; charset=utf-8; boundary=__X_PAW_BOUNDARY__
Host: 138.68.48.6:8080
Connection: close
User-Agent: Paw/3.0.12 (Macintosh; OS X/10.11.6) GCDHTTPRequest

```

> The above command returns JSON structured like this:

```json

{
	"affirmationId":4,
	"phrase":"I feel joy and contentment in this moment right now.",
	"rating":2,
	"categoryId":1
}

```

### HTTP Request

`GET http://138.68.48.6:8080/affirmation-project/affirmationservice/affirmations/{affirmaitonID}`

### URL Parameters

Parameter | Description
--------- | -----------
affirmaitonID | The ID of the affirmation to retrieve

## Affirmation Response

Parameter | type | Description
--------- | ------- | -----------
affirmationId | int | If set to true, the result will also include cats.
phrase | String | If set to false, the result will include kittens that have already been adopted.
rating | int | If set to false, the result will include kittens that have already been adopted.
categoryId | int | If set to false, the result will include kittens that have already been adopted.