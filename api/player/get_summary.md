---
title: "GET /api/player/<:steam_id_64>/summary"
sidebar: mydoc_sidebar
permalink: /api/player/get_summary
folder: mydoc
---

## Description

The `summary` endpoint returns a JSON object containing a curry of statistics, or "fun facts", for the given player.

## Example Response
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

## Specification

This endpoint requires a valid Steam ID in 64-bit format.

Within the `data` field of this response, the following information is expected:

|       Index        | Description                                                                                                     | Type     |
|:------------------:|-----------------------------------------------------------------------------------------------------------------|----------|
| `kills`            | Total number of kills earned by the player                                                                      | int      |
| `kills_received`   | Total number of kills with the player as the victim                                                             | int      |
| `suicides`         | Total number of instances of player using console commands to suicide                                           | int      |
| `connections`      | Total number of instances of the player connecting to the server (but not necessarily spawning into the server) | int      |
| `ents`             | Total number of entities spawned by the player                                                                  | int      |
| `tools`            | Total number of times the player has used (clicked with) the tool gun                                           | int      |
| `kicks`            | Total number of kicks issued by the player                                                                      | int      |
| `kicks_received`   | Total number of times the player has been kicked from the server                                                | int      |
| `bans`             | Total number of bans issued by the player                                                                       | int      |
| `bans_received`    | Total number of times the player has been banned from the server                                                | int      |
| `killed_bys`       | Total number of times the player has died due to non-player damage                                              | int      |
| `chats`            | Total number of chat messages sent by the player (Only chat messages sent in "all" or "team" chats are counted) | int      |
| `first_join_date`  | ISO-8601 formatted datetime string of the earliest recorded connection from the player                          | datetime |
