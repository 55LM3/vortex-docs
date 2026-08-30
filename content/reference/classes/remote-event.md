---
title: RemoteEvent
description: An event that sends information between client and server.
---

## Summary

Can be used to communicate from the server to a client (or all of them) and vice-versa.

For more additional information, see [RemoteFunction](https://create.playvortex.io/reference/classes/remote-function/).

### Example

```luau
-- server

local ReplicatedStorage = game:GetService("ReplicatedStorage")
local Players = game:GetService("Players")

local MyRemote = ReplicatedStorage:WaitForChild("MyRemote") -- WaitForChild is very important!

-- fire to a specific player
local random_player = Players:GetChildren()[math.random(1, #Players:GetChildren())]
MyRemote:FireClient(random_player, "Message coming from the server!")

-- fire to all players
MyRemote:FireAllClients("Minions, tonight, we'll steal the moon!!!")

-- receiving data from a specific player
function reply_received(player, reply)
    print("Reply received from ".. player.Name.. ": ".. reply)
end

MyRemote.OnServerEvent:Connect(reply_received)

```

```luau
-- client

local ReplicatedStorage = game:GetService("ReplicatedStorage")

local MyRemote = ReplicatedStorage:WaitForChild("MyRemote") -- WaitForChild is very important!

function received_msg(msg)
    print("Message received: ".. msg.. ". Replying.")
    MyRemote:FireServer("Copy that.")
end

MyRemote.OnClientEvent:Connect(received_msg)
```

## Methods

- `FireAllClients(arguments: Tuple) : ()` - Fires data to all clients;
- `FireClient(player: Player, arguments: Tuple) : ()` - Fires from the server to the client data;
- `FireServer(arguments: Tuple) : ()` - Fires from the client to the server data.

## Events

- `OnClientEvent(arguments: Tuple) : Signal` - Fired when the client received data from the server;
- `OnServerEvent(player: [Player](https://create.playvortex.io/reference/classes/player/), arguments: Tuple) : Signal` - Fired when the server received data from the client;