---
title: API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - shell
  - ruby
  - python
  - javascript

toc_footers:
  - <a href='https://github.com/lord/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true
---

# Introduction

Welcome to the Exteros API! You can use our API to access Exteros API endpoints, which can get information on Customer Traffic and Staff in our database.

We have language bindings in Shell, Ruby, Python, and JavaScript! You can view code examples in the dark area to the right, and you can switch the programming language of the examples with the tabs in the top right.

# Authentication

> To authorize, use this code:

```ruby
require 'exteros'

api = Exteros::APIClient.authorize!('YOUR_API_KEY')
```

```python
import exteros

api = exteros.authorize('YOUR_API_KEY')
```

```shell
# With shell, you can just pass the correct header with each request
curl "api_endpoint_here"
  -H "Authorization: YOUR_API_KEY"
```

```javascript
const exteros = require('exteros');

let api = exteros.authorize('YOUR_API_KEY');
```

> Make sure to replace `YOUR_API_KEY` with your API key.

Exteros uses API keys to allow access to the API. You can register a new Exteros API key at our [developer portal](https://dashboard.exteros.com).

Exteros expects for the API key to be included in all API requests to the server in a header that looks like the following:

`Authorization: YOUR_API_KEY`

<aside class="notice">
You must replace <code>YOUR_API_KEY</code> with your personal API key.
</aside>

# Traffic

## Get Impression Counts

```ruby
require 'exteros'

api = Exteros::APIClient.authorize!('YOUR_API_KEY')
api.exteros.get
```

```python
import exteros

api = exteros.authorize('YOUR_API_KEY')
api.exteros.get()
```

```shell
curl "https://api.exteros.com/v1/traffic/impression-counts/madison-ave/2020-01-01"
  -H "Authorization: YOUR_API_KEY"
```

```javascript
const exteros = require('exteros');

let api = exteros.authorize('YOUR_API_KEY');
let exteros = api.exteros.get();
```

> The above command returns JSON structured like this:

```json
[
  {
    "id": 1,
    "name": "MadisonAve",
    "type": "groundfloor",
  },
  {
    "id": 2,
    "name": "5thAve",
    "type": "groundfloor",
  }
]
```

This endpoint retrieves all customers.

### HTTP Request

`GET https://api.exteros.com/v1/traffic/impression-counts/<location>/<date>`

### Query Parameters

Parameter |  Default  | Description
--------- | ------- | -----------
'interval' 

### URL Parameters

Parameter | Description
--------- | -----------
location | The name of a store, shop, or specific zone/region to retrieve.
date | Date of Customer Traffic to retrieve. Use format “yyyy-MM-dd".

## Get Discovery Traffic

```ruby
require 'exteros'

api = Exteros::APIClient.authorize!('YOUR_API_KEY')
api.exteros.get
```

```python
import exteros

api = exteros.authorize('YOUR_API_KEY')
api.exteros.get()
```

```shell
curl "https://api.exteros.com/v1/traffic/discovery-counts/madison-ave/2020-01-01"
  -H "Authorization: YOUR_API_KEY"
```

```javascript
const exteros = require('exteros');

let api = exteros.authorize('YOUR_API_KEY');
let exteros = api.exteros.get();
```

> The above command returns JSON structured like this:

```json
[
  {
    "id": 1,
    "name": "MadisonAve",
    "type": "groundfloor",
  },
  {
    "id": 2,
    "name": "5thAve",
    "type": "groundfloor",
  }
]
```

This endpoint retrieves all customers.

### HTTP Request

`GET https://api.exteros.com/v1/traffic/discovery-counts/<location>/<date>`

### Query Parameters

Parameter |  Default  | Description
--------- | ------- | -----------
location | string | The name of a store, shop, or specific zone/region.
date | date | Date of Customer Traffic. When using a format like “yyyy-MM-dd’T’HH:mm:ss’Z’”, always use GMT time. When using a format like “yyyy-MM-dd’T’HH:mm:ss”, you should use local time and  specify the time zone.

### URL Parameters

Parameter | Description
--------- | -----------
location | The name of a store, shop, or specific zone/region to retrieve.
date | Date of Customer Traffic to retrieve. Use format “yyyy-MM-dd".

## Get Engagement Traffic

```ruby
require 'exteros'

api = Exteros::APIClient.authorize!('YOUR_API_KEY')
api.exteros.get
```

```python
import exteros

api = exteros.authorize('YOUR_API_KEY')
api.exteros.get()
```

```shell
curl "https://api.exteros.com/v1/traffic/engagement-counts/madison-ave/2020-01-01"
  -H "Authorization: YOUR_API_KEY"
```

```javascript
const exteros = require('exteros');

let api = exteros.authorize('YOUR_API_KEY');
let exteros = api.exteros.get();
```

> The above command returns JSON structured like this:

```json
[
  {
    "id": 1,
    "name": "MadisonAve",
    "type": "groundfloor",
  },
  {
    "id": 2,
    "name": "5thAve",
    "type": "groundfloor",
  }
]
```

This endpoint retrieves all customers.

### HTTP Request

`GET https://api.exteros.com/v1/traffic/engadgment-counts/<location>/<date>`

### Query Parameters

Parameter |  Default   | Description
--------- | ------- | -----------
location | string | The name of a store, shop, or specific zone/region.
date | date-time | Date of Customer Traffic. When using a format like “yyyy-MM-dd’T’HH:mm:ss’Z’”, always use GMT time. When using a format like “yyyy-MM-dd’T’HH:mm:ss”, you should use local time and  specify the time zone.

### URL Parameters

Parameter | Description
--------- | -----------
location | The name of a store, shop, or specific zone/region to retrieve.
date | Date of Customer Traffic to retrieve. Use format “yyyy-MM-dd".

## Get Interaction Traffic

```ruby
require 'exteros'

api = Exteros::APIClient.authorize!('YOUR_API_KEY')
api.exteros.get
```

```python
import exteros

api = exteros.authorize('YOUR_API_KEY')
api.exteros.get()
```

```shell
curl "https://api.exteros.com/v1/traffic/interaction-counts/madison-ave/2020-01-01"
  -H "Authorization: YOUR_API_KEY"
```

```javascript
const exteros = require('exteros');

let api = exteros.authorize('YOUR_API_KEY');
let exteros = api.exteros.get();
```

> The above command returns JSON structured like this:

```json
[
  {
    "id": 1,
    "name": "MadisonAve",
    "type": "groundfloor",
  },
  {
    "id": 2,
    "name": "5thAve",
    "type": "groundfloor",
  }
]
```

This endpoint retrieves all customers.

### HTTP Request

`GET https://api.exteros.com/v1/traffic/interaction-counts/<location>/<date>`

### Query Parameters

Parameter |  Default   | Description
--------- | ------- | -----------
location | string | The name of a store, shop, or specific zone/region.
date | date-time | Date of Customer Traffic. When using a format like “yyyy-MM-dd’T’HH:mm:ss’Z’”, always use GMT time. When using a format like “yyyy-MM-dd’T’HH:mm:ss”, you should use local time and  specify the time zone.

# Locations

## Get Locations

```ruby
require 'exteros'

api = Exteros::APIClient.authorize!('YOUR_API_KEY')
api.exteros.get
```

```python
import exteros

api = exteros.authorize('YOUR_API_KEY')
api.exteros.get()
```

```shell
curl "https://api.exteros.com/v1/locations"
  -H "Authorization: YOUR_API_KEY"
```

```javascript
const exteros = require('exteros');

let api = exteros.authorize('YOUR_API_KEY');
let exteros = api.exteros.get();
```

> The above command returns JSON structured like this:

```json
[
  {
    "id": 1,
    "brand": "Exteros"
    "name": "MadisonAve",
    "type": "store",
  },
  {
    "id": 2,
    "brand": "Exteros"
    "name": "WomensDepartment",
    "type": "groundfloor",
    "parent": 1,
  },
  {
    "id": 3,
    "brand": "Exteros"
    "name": "MensDepartment",
    "type": "secondfloor",
    "parent": 1,
  },
  {
    "id": 4,
    "brand": "Exteros"
    "name": "5thAve",
    "type": "popup",
  }
]
```

This endpoint retrieves all customers.

### HTTP Request

`GET https://api.exteros.com/v1/locations`

## Get Location Info

```ruby
require 'exteros'

api = Exteros::APIClient.authorize!('YOUR_API_KEY')
api.exteros.get
```

```python
import exteros

api = exteros.authorize('YOUR_API_KEY')
api.exteros.get()
```

```shell
curl "https://api.exteros.com/v1/locations/info/madison-ave"
  -H "Authorization: YOUR_API_KEY"
```

```javascript
const exteros = require('exteros');

let api = exteros.authorize('YOUR_API_KEY');
let exteros = api.exteros.get();
```

> The above command returns JSON structured like this:

```json
[
  {
    "lastUpdate": "2020-05-30T09:30:10Z"
  }
]
```

This endpoint retrieves all customers.

### HTTP Request

`GET https://api.exteros.com/v1/locations/info/<location>`

### URL Parameters

Parameter | Description
--------- | -----------
location | The name of a store, shop, or specific zone/region to retrieve.

## Get Last Location Update

```ruby
require 'exteros'

api = Exteros::APIClient.authorize!('YOUR_API_KEY')
api.exteros.get
```

```python
import exteros

api = exteros.authorize('YOUR_API_KEY')
api.exteros.get()
```

```shell
curl "https://api.exteros.com/v1/locations/last-update/madison-ave"
  -H "Authorization: YOUR_API_KEY"
```

```javascript
const exteros = require('exteros');

let api = exteros.authorize('YOUR_API_KEY');
let exteros = api.exteros.get();
```

> The above command returns JSON structured like this:

```json
[
  {
    "lastUpdate": "2020-05-30T09:30:10Z"
  }
]
```

This endpoint retrieves all customers.

### HTTP Request

`GET https://api.exteros.com/v1/locations/last-update/<location>`

### Query Parameters

Parameter |  Default   | Description
--------- | ------- | -----------
location | string | The name of a store, shop, or specific zone/region.

### URL Parameters

Parameter | Description
--------- | -----------
location | The name of a store, shop, or specific zone/region to retrieve.
