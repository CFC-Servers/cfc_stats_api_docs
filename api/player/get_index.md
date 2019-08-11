---
title: "GET /api/player/<:steam_id_64>/"
sidebar: mydoc_sidebar
permalink: /api/player/get_index
folder: mydoc
---

## Description

The index of a given player returns a JSON object containing information about the player database object

## Example Response
```js
{  
    "id": 134,
    "steam_id": "STEAM_0:0:21170873",
    "created_at": "2019-07-11T07:36:45.000Z"
}
```

## Specification

Within the response, the following information is expected:

|       Index        | Description                                                                                                     | Type      |
|:------------------:|-----------------------------------------------------------------------------------------------------------------|-----------|
| `id`               | The database id of the player                                                                                   |  integer  |
| `steam_id`         | The Steam ID in of the player in 32-bit format                                                                  |  string   |
| `created_at`       | ISO-8601 formatted datetime of when the player was created in the database                                      |  string   |
