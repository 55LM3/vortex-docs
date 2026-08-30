---
title: Client and Server
description: Explains the client and server
---

Vortex games operate with a client-server model.
- Server: The server is the authoritative computer that runs the actual game and is the source of the game's state.
- Client: A client is a local copy of the game running on a player's device.

## Server
The server is the authoritative side of the game. It runs separately from the player’s device and is responsible for managing the actual state of the game, such as player data, game rules, damage, money, and other things that need to be trusted and synchronized between players.

Server-side code is run from [Scripts](https://create.playvortex.io/reference/classes/script/).

## Client
The client is the player’s side of the game. It runs on the player’s device and is responsible for things that the player directly sees and interacts with, such as rendering the world, displaying UI, playing animations, and receiving input from the player.

Client-side code is run from [LocalScripts](https://create.playvortex.io/reference/classes/localscript/).

---

Whenever handling `Client → Server` remotes, make sure to properly validate the data given by the client. A general rule of thumb is to let the client signal intent, not make any decisions about actual state itself. E.g.:
  - Bad: Player clicks a buy button. On their client, they subtract their own money, give themselves the item, the inform the server of the transaction that occurred.
  - Good: Player clicks a buy button. Client informs the server of its intent. Server validates if player has enough money and, if they do, changes their money and gives them the item.
