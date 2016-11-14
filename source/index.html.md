---
title: Affirmation Generator API

language_tabs:
  - JavaScript
  - Swift

toc_footers:
  - <a href='#'>Sign Up for a Developer Key</a>
  - <a href='https://github.com/tripit/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true
---

# Introduction

Welcome to the Affirmation API! You can use our API to access Affirmation API endpoints, which can send you an affirmation (or affirmations) from different affirmation categories in our database.

We have language bindings in [Shell, Ruby, and Python]! You can view code examples in the dark area to the right, and you can switch the programming language of the examples with the tabs in the top right.

This example API documentation page was created with [Slate](https://github.com/tripit/slate).

# Authentication

> To authorize, use this code:

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
```

```shell
# With shell, you can just pass the correct header with each request
curl "api_endpoint_here"
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
```

> Make sure to replace `meowmeowmeow` with your API key.

Affirmation Generator uses basic authentication to allow access to the API with a user name and password to generate basic authorization. You can request a user name and password by emailing [The Developers](todd.kinsman@gmail.com).

Affirmation Generator expects the authorization header to be included in all API requests to the server in a header that looks like the following:

`Authorization: meowmeowmeow`

<aside class="notice">
You must replace <code>meowmeowmeow</code> with your personal API key.
</aside>

# Affirmations

## Get All Affirmations

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.get
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.get()
```

```shell
curl "http://example.com/api/kittens"
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let kittens = api.kittens.get();
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
Remember — a happy kitten is an authenticated kitten!
</aside>

## Get Affirmation by Category

`GET http://138.68.48.6:8080/affirmationservice/affirmations/categories/{category name parameter}`

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

## Get List of Popular Affirmations

`GET http://138.68.48.6:8080/affirmation-project/affirmationservice/affirmations/`

*Instructions to come*

[Affirmation Response Parameters](#affirmation-response)

## Up-vote an Affirmation 

`PUT http://138.68.48.6:8080/affirmation-project/affirmationservice/affirmations/upvote/{affirmationId}`

You must know the id of the affirmation you wish to *upvote* in order to create a valid request.

### URL Parameters

Parameter | Type | Description
--------- | ----------- | --------
affirmationId | int | The id of the affirmation you wish to *upvote*.

[Affirmation Response Parameters](#affirmation-response)

## Down-vote an Affirmation 

`PUT http://138.68.48.6:8080/affirmation-project/affirmationservice/affirmations/downvote/{affirmationId}`

You must know the id of the affirmation you wish to *downvote* in order to create a valid request.

### URL Parameters

Parameter | Type | Description
--------- | ----------- | --------
affirmationId | int | The id of the affirmation you wish to *downvote*.

[Affirmation Response Parameters](#affirmation-response)

## Get a Specific Affirmation

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.get(2)
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.get(2)
```

```shell
curl "http://example.com/api/kittens/2"
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let max = api.kittens.get(2);
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "name": "Max",
  "breed": "unknown",
  "fluffiness": 5,
  "cuteness": 10
}
```

This endpoint retrieves a specific kitten.

<aside class="warning">Inside HTML code blocks like this one, you can't use Markdown, so use <code>&lt;code&gt;</code> blocks to denote code.</aside>

### HTTP Request

`GET http://example.com/kittens/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the kitten to retrieve

## Affirmation Response

Parameter | type | Description
--------- | ------- | -----------
affirmationId | int | If set to true, the result will also include cats.
phrase | String | If set to false, the result will include kittens that have already been adopted.
rating | int | If set to false, the result will include kittens that have already been adopted.
categoryId | int | If set to false, the result will include kittens that have already been adopted.