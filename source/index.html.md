---
title: API Reference

language_tabs: # must be one of https://github.com/rouge-ruby/rouge/wiki/List-of-supported-languages-and-lexers
  - JS
  - TS
  - typings
toc_footers:
  - <a href='https://discord.js.org/docs/packages/discord.js/14.15.2'>Discord.JS Documentation</a>
  - <a href='https://www.typescriptlang.org/docs/handbook/'>TypeScript Documentation</a>
  - <a href='https://nodejs.org/api/'>Node.JS Documentation</a>
  - <a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript'>JavaScript Documentation</a>


includes:
  - errors

search: true

code_clipboard: true

meta:
  - name: description
    content: Documentation for Botto Slime
---

# Botto Slime Documentation

Welcome asdf123 to the Kittn API! You can use our API to access Kittn API endpoints, which can get information on various cats, kittens, and breeds in our database.

We have language bindings in Shell, Ruby, Python, and JavaScript! You can view code examples in the dark area to the right, and you can switch the programming language of the examples with the tabs in the top right.

This example API documentation page was created with [Slate](https://github.com/slatedocs/slate). Feel free to edit it and use it as a base for your own API's documentation.

# Setup

# Styles
## ESLint


# Extensions
## Discord.Client Mixins
Blah blah blah we add items to the client 
### `settings`
<aside class="notice">
See <a href="#settings-2">lib/settings</a> for more details
</aside>

### `afkChecks`

### `afkModules`
<aside class="warning">
This is deprecated and liable to removed in the near future. Use <a href="#afkChecks">afkChecks</a> whenever you need to access live afks.
</aside>

### `adminUsers`

### `emojiServers`

### storedEmojis

## Discord.GuildMember
## Discord.Guild
## Discord.Message
## Discord.ChatInputCommandInteraction

# lib/
Home to any files that aren't directly attached to a single command (extensions) or any functionality that could quality as a service (modmail). If some functionality is best split up into several files, that can also be placed as a subfolder within here (afks).

## extensions & discordExtensions
<aside class="notice">
See <a href="#extensions">Extensions</a> for information about our current class/function extensions.
</aside>

## settings
<details class="typedef">
  <summary>Guild Typings</summary>
  Specific settings properties can be found in the config-types repository.
</details>

```ts
type GuildSettings = {;
  roles: RolesSettings;
  channels: ChannelsSettings;
  voice: VoiceSettings;
  voiceprefixes: VoiceprefixesSettings;
  backend: BackendSettings;
  numerical: NumericalSettings;
  runreqs: RunreqsSettings;
  autoveri: AutoveriSettings;
  vetverireqs: VetverireqsSettings;
  points: PointsSettings;
  raiding: RaidingSettings;
  lists: ListsSettings;
  strings: StringsSettings;
  quotapoints: QuotapointsSettings;
  modmail: ModmailSettings;
  supporter: SupporterSettings;
  rolePermissions: RolePermissionsSettings;
  commands: { [key: string]: boolean };
  checkPanels: { [key: string]: boolean };
  checkRoles: { [key: string]: string[] };
  checkUserExceptions: { [key: string]: string[] };
  checkRoleExceptions: { [key: string]: string[] };
  removeRoleFromUserWithRoles: { [key: string]: string[] };
  addRolesToUsersWithRoles: { [key: string]: string[] };
  checkStrings: { [key: string]: string };
  commandsRolePermissions: { [key: string]: RolesType };
};
```
## logger
f
## modmail
e
## parseLogger
d
## pointLogger
c
## proxy
b
## realmEyeScrape
a

# Authentication

> To authorize, use this code:

```python
import kittn

api = kittn.authorize('meowmeowmeow')
```


```shell
# With shell, you can just pass the correct header with each request
curl "api_endpoint_here" \
  -H "Authorization: meowmeowmeow"
```

```js
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
```

> Make sure to replace `meowmeowmeow` with your API key.

Kittn uses API keys to allow access to the API. You can register a new Kittn API key at our [developer portal](http://example.com/developers).

Kittn expects for the API key to be included in all API requests to the server in a header that looks like the following:

`Authorization: meowmeowmeow`

<aside class="notice">
You must replace <code>meowmeowmeow</code> with your personal API key.
</aside>

# Kittens

## Get All Kittens

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
curl "http://example.com/api/kittens" \
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

This endpoint retrieves all kittens.

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

## Get a Specific Kitten

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
curl "http://example.com/api/kittens/2" \
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

## Delete a Specific Kitten

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.delete(2)
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.delete(2)
```

```shell
curl "http://example.com/api/kittens/2" \
  -X DELETE \
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
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

