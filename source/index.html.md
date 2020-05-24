---
title: API Documentation

language_tabs: # must be one of https://git.io/vQNgJ
  - shell
  - ruby
  - python
  - javascript

toc_footers:
  - <a href='mailto:contact@inokufu.com'>Ask for a Developer Key</a>
  - <a href='https://github.com/slatedocs/slate'>Powered by Slate</a>

includes:
  - errors

search: true
---

# Introduction

Welcome to the Inokufu API Cloud! This API documentation shows you how to access our API endpoints, which can get information about Learning Objects in our database.

We have language bindings in Shell, Ruby, Python, and JavaScript! You can view code examples in the dark area to the right, and you can switch the programming language of the examples with the tabs in the top right.

# Authentication

> To authorize, use this code:

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('YOU-SHALL-NOT-PASS')
```

```python
import kittn

api = kittn.authorize('YOU-SHALL-NOT-PASS')
```

```shell
# With shell, you can just pass the correct header with each request
curl "api_endpoint_here"
  -H "Authorization: YOU-SHALL-NOT-PASS"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('YOU-SHALL-NOT-PASS');
```

> Make sure to replace `YOU-SHALL-NOT-PASS` with your personal Developer API key.

Inokufu API Cloud uses API keys to allow access to the API. You can register for a Developer API key by sending us an email at [contact@inokufu.com](mailto:contact@inokufu.com).

Free Developer API key are available and let you make up to 1000 request per month.

For higher request quota we offer paid usage plan starting at 100 $/month. Feel free to get in touch at [contact@inokufu.com](mailto:contact@inokufu.com) we are fully dedicated to our customers success. Education is more than a mere business. We believe in better education access and efficiency. We believe in technology. We believe in better Educational Technology (EdTech) to push the boundaries of education access and efficiency.

Inokufu API Cloud expects for the API key to be included in all API requests to the server in a header that looks like the following:

`Authorization: YOU-SHALL-NOT-PASS`

<aside class="notice">
You must replace <code>YOU-SHALL-NOT-PASS</code> with your personal Developer API key.
</aside>

# Learning Objects (LO)

## List of LO

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('YOU-SHALL-NOT-PASS')
api.kittens.get
```

```python
import kittn

api = kittn.authorize('YOU-SHALL-NOT-PASS')
api.kittens.get()
```

```shell
curl "http://example.com/api/kittens"
  -H "Authorization: YOU-SHALL-NOT-PASS"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('YOU-SHALL-NOT-PASS');
let kittens = api.kittens.get();
```

> The above command returns JSON structured like this:

```json
[
  {
    "id": 1,
    "name": "Fluffums",
    "breed": "calico",
    "fluffiness": 6,
    "cuteness": 7
  },
  {
    "id": 2,
    "name": "Max",
    "breed": "unknown",
    "fluffiness": 5,
    "cuteness": 10
  }
]
```

This endpoint retrieves a list of LO. 

LO can be filtered by keywords, type, bloom step and language (english or french for now).

### HTTP Request

`GET http://example.com/api/kittens`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
include_cats | false | If set to true, the result will also include cats.
available | true | If set to false, the result will include kittens that have already been adopted.

<aside class="success">
Remember — a happy kitten is an authenticated kitten!
</aside>

## LO details

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('YOU-SHALL-NOT-PASS')
api.kittens.get(2)
```

```python
import kittn

api = kittn.authorize('YOU-SHALL-NOT-PASS')
api.kittens.get(2)
```

```shell
curl "http://example.com/api/kittens/2"
  -H "Authorization: YOU-SHALL-NOT-PASS"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('YOU-SHALL-NOT-PASS');
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

# Credits

This API documentation page was created with [Slate](https://github.com/slatedocs/slate). Feel free to check their awesome repo on Github!

