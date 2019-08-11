---
title: "GET /api/player/<:steam_id_64>/"
sidebar: mydoc_sidebar
permalink: /api/player/get_index
folder: mydoc
---

## Description

The player index returns a JSON object containing a positive phrase of encouragement

## Example Response
```js
{  
    "response": "good job"
}
```

## Specification

Within the response, the following information is expected:

|       Index        | Description                                                                                                     | Type     |
|:------------------:|-----------------------------------------------------------------------------------------------------------------|----------|
| `response`         | A positive phrase of encouragement                                                                              |  string  |
