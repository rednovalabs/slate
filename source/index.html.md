---
title: storEDGE REST API v2

language_tabs: # must be one of https://git.io/vQNgJ
- csharp
- ruby
- python
- javascript
- shell

toc_footers: []

highlight_theme: github.slate

includes:
  - errors

search: true

code_clipboard: true

meta:
  - name: storEDGE REST API v2
    content: Documentation for the storEDGE REST API V2
---

<h1 id="storEDGEAPIV2">storEDGE REST API v2</h1>

It does stuff.
The storEDGE API is a REST API.

Base URLs:

All communication is done over HTTPS, there is no non-secure access. All storEDGE URL’s adhere to the following format:

- `https:///:version_identifier/:facility_id/:resource((/:resource_id)((/:subresource)(/:subresource_id)))`

A URL in practice would be something like:

- `https://api.storedgefms.com/v1/843eee43­55b7­4b25­85c4­c555ba7f43fa/ledgers/2c7b16bb­-a760­-4938­-b942­44f719e-05529`


# Authentication
> **To authorize, use this code:**

```ruby
require 'storedge_client'

api = StorEdgeClient.new({key: 'MyCoolAuthKey', secret: 'MyCoolAuthSecret'})
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
```

```shell
# With shell, you can just pass the correct header with each request
curl "api_endpoint_here" \
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
```

```csharp
StoreEdgeClientCredential storEdgeCredentials = new storEdgeCredential("MyCoolAuthKey", "MyCoolAuthSecret");
StorEdgeClient client = new StorEdgeClient(fmsCredentials);
```

> Make sure to replace credentials using your key and secret.

The storEDGE REST API V2 uses OAuth 1.0 as its authentication mechanism. Whereas in many OAuth implementations you would have three steps (application<->service, service<->user, service<->application), storEDGE uses only one leg (application<->service), hence the term "one-legged". For a description of the various OAuth 1.0 flows, please see [https://github.com/Mashape/mashape-oauth/blob/master/FLOWS.md](https://github.com/Mashape/mashape-oauth/blob/master/FLOWS.md)

You will need three pieces of information to communicate with the API:

API access ID This ID is attached to a particular company and is created by your users and provided to you by them. Put this in your OAuth config as the consumer key.
API secret key Also provided by your users. Put this in your OAuth config as the consumer secret.
Facility ID Your users will provide this to you as well. Put this directly into the URL.

### Formats and Headers

The storEDGE API sends and receives data in JSON format. For more info on JSON, check out [http://json.org](http://json.org).

It is highly recommended that the standard Content­-Type and Accept headers be included on every storEDGE API call. Since the format is JSON, the values of these headers should be application/json. Some calls may not succeed without these headers.

<aside class="notice">
You must replace <code>MyCoolAuthKey</code> and <code>MyCoolAuthSecret</code>with your personal API key and secret, respectably.
</aside>


# Channels

## Get All Channels

<!-- ## get__v1_companies_137202df-0f06-4e5a-bc6c-722a05bbcd0e_channels -->

> **Get Channels Code Example**

```csharp
StoreEdgeClientCredential storEdgeCredentials = new StoreEdgeClientCredential("MyCoolAuthKey", "MyCoolAuthSecret");
StorEdgeClient client = new StorEdgeClient(storEdgeCredentials);
client.channels;
```

```ruby
StorEdgeClient.new({key: 'MyCoolAuthKey', secret: 'MyCoolAuthSecret'}).channels
```

`GET /v1/companies/:company_id/channels`

<h3 id="get__v1_companies_137202df-0f06-4e5a-bc6c-722a05bbcd0e_channels-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|**company_id**|query|string|true|The company id|
|**fields**|query|object|false|Name the fields you wish returned by the response|

> **Request** /v1/companies/:company_id/channels

```json
[
  {
    "id": "535204dh-0k06-6u3h-yc9r-722a05xitd9y"
  }
]
```

> **Request** /v1/companies/:company_id/channels?fields[channel]=id,name,company_id,channel_rate_ids

```json
[
  {
    "id": "535204dh-0k06-6u3h-yc9r-722a05xitd9y",
    "name": "Web",
    "company_id": "137202df-0f06-4e5a-bc6c-722a05bbcd0e",
    "channel_rate_ids": [
      "137202df-0f06-4e5a-bc6c-722a05bbcd0e"
    ]
  }
]
```

<h3 id="get__v1_companies_137202df-0f06-4e5a-bc6c-722a05bbcd0e_channels-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|None|

<h3 id="get__v1_companies_137202df-0f06-4e5a-bc6c-722a05bbcd0e_channels-responseschema">Response Schema</h3>

|Field|Type|Meaning|
|---|---|---|
| **id** | uuid | The channel id |
| **name** | string | The name assigned for the channel |
| **company_id** | uuid | The id of the company associated to the channel |
|**channel_rate_ids** | array(uuid) | A list of the channel rate ids associated to the channel |

<aside class="success">
This is a green success section looks like
</aside>
