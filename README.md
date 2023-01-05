# Multigames Abstract
By **[Christian Deacon](https://github.com/gamemann)**  
Created on **January 4th, 2023**

## Overview
This document will serve as an abstract for implementing support for rotation of games and game modes inside of any given game engine for multiplayer servers. Game engines that would benefit from this implementation include the following.

* [Godot Engine](https://godotengine.org/)
* [Unity](https://unity.com/)
* [Unreal Engine](https://unrealengine.com/)

## Design
We have the **client**, which is typically a player/real person and the **game server** whose responsibilities include everything multiplayer-related from sending data back and forth between the client and game server, syncing data between all clients, and handling other stateful data (e.g. physics).

With our approach, before clients may fully load into the server, the server requires the client to download all *content* the client does not have for a given game or game mode. Content include assets such as models, materials, objects, and prefabs along with scenes/maps. In this case, the game server would force the client to download all content automatically using secure methods such as `HTTPS`. After all content is downloaded, the client mounts the content and is loaded into the game server.

There are existing tools and frameworks out there such as [Steam Workshop](https://steamcommunity.com/workshop/) that does something similar to this. However, only supports content specifically inside of a game such as community-made content like maps, models and materials.
