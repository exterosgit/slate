---
title: API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - shell
  - ruby
  - python
  - javascript

toc_footers:
  - <a href='#'>Sign Up for a Developer Key</a>
  - <a href='https://github.com/lord/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true
---

# Introduction

Welcome to the Exteros API! You can use our API to access Exteros API endpoints, which can get information on various cats, exteros, and breeds in our database.

We have language bindings in Shell, Ruby, Python, and JavaScript! You can view code examples in the dark area to the right, and you can switch the programming language of the examples with the tabs in the top right.

# Authentication

> To authorize, use this code:

```ruby
require 'exteros'

api = Exteros::APIClient.authorize!('meowmeowmeow')
```

```python
import exteros

api = exteros.authorize('meowmeowmeow')
```

```shell
# With shell, you can just pass the correct header with each request
curl "api_endpoint_here"
  -H "Authorization: meowmeowmeow"
```

```javascript
const exteros = require('exteros');

let api = exteros.authorize('meowmeowmeow');
```

> Make sure to replace `meowmeowmeow` with your API key.

Exteros uses API keys to allow access to the API. You can register a new Exteros API key at our [developer portal](http://example.com/developers).

Exteros expects for the API key to be included in all API requests to the server in a header that looks like the following:

`Authorization: meowmeowmeow`

<aside class="notice">
You must replace <code>meowmeowmeow</code> with your personal API key.
</aside>

# Customers

## Get Customers

```ruby
require 'exteros'

api = Exteros::APIClient.authorize!('meowmeowmeow')
api.exteros.get
```

```python
import exteros

api = exteros.authorize('meowmeowmeow')
api.exteros.get()
```

```shell
curl "http://api.exteros.com"
  -H "Authorization: meowmeowmeow"
```

```javascript
const exteros = require('exteros');

let api = exteros.authorize('meowmeowmeow');
let exteros = api.exteros.get();
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

This endpoint retrieves all exteros.

### HTTP Request

`GET http://api.exteros.com`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
include_cats | false | If set to true, the result will also include cats.
available | true | If set to false, the result will include exteros that have already been adopted.

<aside class="success">
Remember — a happy kitten is an authenticated kitten!
</aside>

## Get a Specific Customer

```ruby
require 'exteros'

api = Exteros::APIClient.authorize!('meowmeowmeow')
api.exteros.get(2)
```

```python
import exteros

api = exteros.authorize('meowmeowmeow')
api.exteros.get(2)
```

```shell
curl "http://example.com/api/exteros/2"
  -H "Authorization: meowmeowmeow"
```

```javascript
const exteros = require('exteros');

let api = exteros.authorize('meowmeowmeow');
let max = api.exteros.get(2);
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

`GET http://example.com/exteros/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the kitten to retrieve
