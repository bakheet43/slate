---
title: API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - shell
  # - ruby
  # - python
  # - javascript

# toc_footers:
#   - <a href='#'>Sign Up for a Developer Key</a>
#   - <a href='https://github.com/slatedocs/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true

code_clipboard: true
---

# Introduction

Welcome to the EnayaPay API! You can use our API to access Payment API endpoints, which can get information on various transactions, making a payment to various providers like card transfer,telecom services and electricity.

We have language bindings in Shell, Rest Api! You can view code examples in the dark area to the right.


# Authentication

> To authorize, use this code:

<!-- ```ruby
require 'Enaya'

api = Enaya::APIClient.authorize!('meowmeowmeow')
```

```python
import Enaya

api = Enaya.authorize('f5db97dc-de22-4a4b-bc22-c8725e5f69e4')
``` -->

```shell
# With shell, you can just pass the correct header with each request
curl "api_endpoint_here" \
  -H "app-key: f5db97dc-de22-4a4b-bc22-c8725e5f69e4"\
  "secret-key":"f5db97dc-de22-4a4b-bc22-c8725e5f69e4"\
  "platform":"web" 
```
<!-- 
```javascript
const Enaya = require('Enaya');

let api = Enaya.authorize('f5db97dc-de22-4a4b-bc22-c8725e5f69e4');
``` -->

> Make sure to replace `f5db97dc-de22-4a4b-bc22-c8725e5f69e4` with your API key. just this is sample api key. contact your account manager to give you the api key.

Enaya uses APP keys and Secret Key to allow access to the API. You can register a new Enaya API key at our [developer portal](http://enayapay.com/).

Enaya expects for the API key to be included in all API requests to the server in a header that looks like the following:

`app-key: f5db97dc-de22-4a4b-bc22-c8725e5f69e4`

<aside class="notice">
You must replace <code>f5db97dc-de22-4a4b-bc22-c8725e5f69e4</code> with your personal API key.
</aside>

# Transfer

## Transfer from card to another

<!-- 
```ruby
require 'Enaya'

api = Enaya::APIClient.authorize!('meowmeowmeow')
api.kittens.get
```

```python
import Enaya

api = Enaya.authorize('meowmeowmeow')
api.kittens.get()
``` -->

```shell
 curl -d '{
	"amount":455,
	"from_card":"4342423432423425",
	"to_card":"5525 5555 5555 5555",
	"expiration_date":"0921",
	"phone_number":"249***********",
	"ipin":"errwqrweradwdsDSDSDDSDsadAS",
	"uuid":"rt55fgfgdssdggdfgdsdsgd"
}' -H "Content-Type: application/json"  -X POST https://sandbox.platform.enayapay.com/api/v2.2/transfer/ 
```

<!-- ```javascript
const Enaya = require('Enaya');

let api = Enaya.authorize('meowmeowmeow');
let kittens = api.kittens.get();
``` -->

> The above command returns JSON structured like this:

```json
{
	"from_card": "************3425",
	"to_card": "***************5555",
	"amount": 455.0,
	"response_status": "Successful",
	"enaya_fee": 0.05
} 
```

This endpoint transfers amount from card to another.

### HTTP Request

`POST https://sandbox.platform.enayapay.com/api/v2.2/transfer`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
amount | double | Amount to be transfered.
from_card | string | card to pay with.
phone_number | string | receiver number.
to_card | string | card to be transfer the amount to or card that recieve the amount.
expiration_date | string | expiration date of the from card, and it should be in format 0921 or mmyy.
ipin | string | ipin of the card to be pay with and it should be send ecnrypted.
uuid | string | uuid string ti be unique for each transaction.

<!-- <aside class="success">
Remember — a happy kitten is an authenticated kitten!
</aside> -->
<!-- 
## Get a Specific Kitten

```ruby
require 'Enaya'

api = Enaya::APIClient.authorize!('meowmeowmeow')
api.kittens.get(2)
```

```python
import Enaya

api = Enaya.authorize('meowmeowmeow')
api.kittens.get(2)
```

```shell
curl "http://example.com/api/kittens/2" \
  -H "Authorization: meowmeowmeow"
```

```javascript
const Enaya = require('Enaya');

let api = Enaya.authorize('meowmeowmeow');
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

## Delete a Specific Kitten

```ruby
require 'Enaya'

api = Enaya::APIClient.authorize!('meowmeowmeow')
api.kittens.delete(2)
```

```python
import Enaya

api = Enaya.authorize('meowmeowmeow')
api.kittens.delete(2)
```

```shell
curl "http://example.com/api/kittens/2" \
  -X DELETE \
  -H "Authorization: meowmeowmeow"
```

```javascript
const Enaya = require('Enaya');

let api = Enaya.authorize('meowmeowmeow');
let max = api.kittens.delete(2);
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "deleted" : ":("
}
```

This endpoint deletes a specific kitten.

### HTTP Request

`DELETE http://example.com/kittens/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the kitten to delete




---------------- -->

