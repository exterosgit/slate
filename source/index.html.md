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

Exteros uses API keys to allow access to the API. You can register a new Exteros API key at our [developer portal](https://developer.exteros.com). Authentication uses the OAuth 2.0 specification.

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
curl "https://api.exteros.com/v1/traffic/impression-counts/madison-ave-store/2020-01-01"
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
    "hr": 9,
    "impressions": 100
  },
  {
    "hr": 10,
    "impressions": 200
  },
  {
    "hr": 11,
    "impressions": 250
  },
  {
    "hr": 12,
    "impressions": 300
  },
  {
    "hr": 13,
    "impressions": 250
  },
  {
    "hr": 14,
    "impressions": 150
  },
  {
    "hr": 15,
    "impressions": 50
  }
]
```

This endpoint retrieves impression counts - the number of people passing by a given location.

### HTTP Request

`GET https://api.exteros.com/v1/traffic/impression-counts/<location>/<date>`

### Query Parameters

Parameter |  Default  | Description
--------- | ------- | -----------
hour | 'all'  | Retrieve impression counts for a specific hour.
interval | 'hour' | Retrieve counts according to the time specified time interval. Options: 'day', 'hour', '15min'


### URL Parameters

Parameter | Description
--------- | -----------
location | The name of a store, shop, or specific zone/region to retrieve.
date | Date of impression Traffic to retrieve. Use format “yyyy-MM-dd".

## Get Discovery Counts

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
curl "https://api.exteros.com/v1/traffic/discovery-counts/madison-ave-store/2020-01-01"
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
    "hr": 9,
    "discoveries": 50
  },
  {
    "hr": 10,
    "discoveries": 150
  },
  {
    "hr": 11,
    "discoveries": 200
  },
  {
    "hr": 12,
    "discoveries": 250
  },
  {
    "hr": 13,
    "discoveries": 200
  },
  {
    "hr": 14,
    "discoveries": 100
  },
  {
    "hr": 15,
    "discoveries": 0
  }
]
```

This endpoint retrieves discovery counts - the number of people spending at least 3 seconds at a given location.

### HTTP Request

`GET https://api.exteros.com/v1/traffic/discovery-counts/<location>/<date>`

### Query Parameters

Parameter |  Default  | Description
--------- | ------- | -----------
hour | 'all'  | Retrieve discovery counts for a specific hour.
interval | 'hour' | Retrieve counts according to the time specified time interval. Options: 'day', 'hour', '15min'


### URL Parameters

Parameter | Description
--------- | -----------
location | The name of a store, shop, or specific zone/region to retrieve.
date | Date of discovery Traffic to retrieve. Use format “yyyy-MM-dd".

## Get Engagement Counts

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
curl "https://api.exteros.com/v1/traffic/engagement-counts/madison-ave-store/2020-01-01"
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
    "hr": 9,
    "engagements": 0
  },
  {
    "hr": 10,
    "engagements": 100
  },
  {
    "hr": 11,
    "engagements": 150
  },
  {
    "hr": 12,
    "engagements": 200
  },
  {
    "hr": 13,
    "engagements": 150
  },
  {
    "hr": 14,
    "engagements": 50
  },
  {
    "hr": 15,
    "engagements": 0
  }
]
```

This endpoint retrieves engagement counts - the number of people spending at least 10 seconds at a given location.

### HTTP Request

`GET https://api.exteros.com/v1/traffic/engadgment-counts/<location>/<date>`

### Query Parameters

Parameter |  Default  | Description
--------- | ------- | -----------
hour | 'all'  | Retrieve engagement counts for a specific hour.
interval | 'hour' | Retrieve counts according to the time specified time interval. Options: 'day', 'hour', '15min'


### URL Parameters

Parameter | Description
--------- | -----------
location | The name of a store, shop, or specific zone/region to retrieve.
date | Date of engagement Traffic to retrieve. Use format “yyyy-MM-dd".

## Get Interaction Counts

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
curl "https://api.exteros.com/v1/traffic/interaction-counts/madison-ave-store/2020-01-01"
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
    "hr": 9,
    "interactions": 0
  },
  {
    "hr": 10,
    "interactions": 50
  },
  {
    "hr": 11,
    "interactions": 100
  },
  {
    "hr": 12,
    "interactions": 150
  },
  {
    "hr": 13,
    "interactions": 100
  },
  {
    "hr": 14,
    "interactions": 0
  },
  {
    "hr": 15,
    "interactions": 0
  }
]
```

This endpoint retrieves interaction counts - the number of people touching or picking up a product at a given location.

### Query Parameters

Parameter |  Default  | Description
--------- | ------- | -----------
hour | 'all'  | Retrieve interaction counts for a specific hour.
interval | 'hour' | Retrieve counts according to the time specified time interval. Options: 'day', 'hour', '15min'


### URL Parameters

Parameter | Description
--------- | -----------
location | The name of a store, shop, or specific zone/region to retrieve.
date | Date of interaction Traffic to retrieve. Use format “yyyy-MM-dd".

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
    "location-name": "madison-ave-store",
  },
  {
    "location-name": "5th-ave-popup",
  }
]
```

This endpoint retrieves all customers.

### HTTP Request

`GET https://api.exteros.com/v1/locations`

### Query Parameters

Parameter |  Default  | Description
--------- | ------- | -----------
info | false  | Retrieve additional information about each location: company/brand, parent location, child locations, type of store/location.

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
curl "https://api.exteros.com/v1/locations/last-update/madison-ave-store"
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
    "last-update": "2020-05-30T09:30:10Z"
  }
]
```

This endpoint retrieves all customers.

### HTTP Request

`GET https://api.exteros.com/v1/locations/last-update/<location>`

### URL Parameters

Parameter | Description
--------- | -----------
location | The name of a store, shop, or specific zone/region to retrieve.
