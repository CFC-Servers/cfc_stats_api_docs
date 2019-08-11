---
title: "Getting started with the CFC Stats API"
keywords: basic usage
tags: [getting_started]
sidebar: mydoc_sidebar
permalink: index.html
summary: How to use the API on a basic level
---

# Basic Information

 - The Base URL for the Statistics API is: `https://stats.cfcservers.org/api/v1/`
 - The API sends and receives information in JSON format
 - This is not a full RESTful API as of right now, it's still under active development
 - All update notifications and updates are released on our Discord; [https://cfcservers.org/discord](https://cfcservers.org/discord)


# Examples

Below are language-specific examples of how to interact with the API. They'll all be performing the same request, a `GET` to `https://stats.cfcservers.org/api/v1/player/76561198002607474/summary` which will return:

```js
{  
   "type":"summary",
   "data":{  
      "kills":6006,
      "kills_received":451,
      "suicides":672,
      "connections":760,
      "ents":63570,
      "tools":43921,
      "kicks":17,
      "kicks_received":0,
      "bans":15,
      "bans_received":0,
      "killed_bys":503,
      "chats":19349,
      "first_join_date":"2015-03-12T20:31:09.000Z"
   }
}
```

## E2
```lua
@persist URL:string
@persist HasMadeRequest

if( first() ) {
	runOnHTTP(1)
	URL = "https://stats.cfcservers.org/api/v1/player/76561198002607474/summary"
	HasMadeRequest = 0
}

if( !HasMadeRequest ) {
	httpRequest(URL)
	HasMadeRequest = 1
}

if( httpClk() ) {
	local response = httpData()

	parsed = jsonParse(response)
}

interval(100)
```

## Lua
```lua
local url = "https://stats.cfcservers.org/api/v1/player/76561198002607474/summary"

http.Fetch( url, function( body )
	local parsed = util.JSONToTable( body )
	print( parsed.data.kills )
end, function( err )
	print( err )
end )
```

## Python
```py
import requests

response = requests.get("https://stats.cfcservers.org/api/v1/player/76561198002607474/summary")

parsed = response.json()

print(parsed["data"]["kills"])
```

## Ruby
```ruby
require "http"

response = HTTP.get("https://stats.cfcservers.org/api/v1/player/76561198002607474/summary")

parsed = JSON.parse(response.body())

puts parsed["data"]["kills"]
```


