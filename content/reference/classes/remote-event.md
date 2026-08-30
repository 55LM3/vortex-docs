---
title: RemoteEvent
description: An event that sends information between client and server.
---

## Summary

Can be used to communicate from the server to a client (or all of them) and
vice-versa.

For more additional information, see
[RemoteFunction](https://create.playvortex.io/reference/classes/remote-function/).

### Example

```luau
-- server

local ReplicatedStorage = game:GetService("ReplicatedStorage")
local Players = game:GetService("Players")
local MyRemote = ReplicatedStorage:WaitForChild("MyRemote") -- WaitForChild is important.

-- The methods are exposed, but Vortex cannot currently obtain a server Player
-- to target, so this Roblox-style targeting block remains illustrative only:
-- local random_player = Players:GetChildren()[math.random(1, #Players:GetChildren())]
-- MyRemote:FireClient(random_player, "Message coming from the server!")
-- MyRemote:FireAllClients("Minions, tonight, we'll steal the moon!!!")

-- `senderId` is a numeric connection identifier in Vortex, not a Player.
local function reply_received(senderId, reply)
    print("Reply received from connection " .. senderId .. ": " .. reply)
end

MyRemote.OnServerEvent:Connect(reply_received)
```

```luau
-- LocalScript

local ReplicatedStorage = game:GetService("ReplicatedStorage")
local MyRemote = ReplicatedStorage:WaitForChild("MyRemote")

function received_msg(msg)
    print("Message received: " .. msg .. ". Replying.")
    MyRemote:FireServer("Copy that.")
end

MyRemote.OnClientEvent:Connect(received_msg)
```

## Methods

- `FireAllClients(arguments: Tuple) : ()` - Fires data to all clients;
- `FireClient(player: Player, arguments: Tuple) : ()` - Fires data from the
  server to a client;
- `FireServer(arguments: Tuple) : ()` - Fires data from the client to the
  server.

## Events

- `OnClientEvent(arguments: Tuple) : Signal` - Fired when the client receives
  data from the server;
- `OnServerEvent(senderId: Number, arguments: Tuple) : Signal` - Fired when
  the server receives data from the client.

## Vortex Studio 0.3.3 notes

- `FireServer` to `OnServerEvent` was confirmed for an editor-authored remote
  in `ReplicatedStorage`.
- Script-created remotes parented into `ReplicatedStorage` were visible to the
  client but did not dispatch to the server handler.
- `FireClient`, `FireAllClients`, and `OnClientEvent` are exposed, but their
  delivery has not yet been established.
- The server `Players` service cannot resolve `senderId` to a Player,
  Character, or Humanoid, so Roblox-style server player-targeting examples do
  not currently apply.
- Instances, including `LocalPlayer` and the character, cannot be sent as
  remote arguments.
