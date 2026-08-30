---
title: RemoteEvent
description: Sends asynchronous data between client and server contexts.
---

## Summary

`RemoteEvent` exposes asynchronous client/server signal endpoints. In Vortex
Studio 0.3.3, client-to-server delivery was confirmed only for a `RemoteEvent`
authored in the editor under `ReplicatedStorage` before play.

```luau
-- Script; use an editor-authored RemoteEvent named KeybindToServer.
local remote = game:GetService("ReplicatedStorage"):WaitForChild("KeybindToServer")

remote.OnServerEvent:Connect(function(senderId, keyName)
    print("Received", keyName, "from connection", senderId)
end)
```

```luau
-- LocalScript
local remote = game:GetService("ReplicatedStorage"):WaitForChild("KeybindToServer")
remote:FireServer("W")
```

## Methods

- `FireServer(...arguments: any): nil` — exposed on the client; delivery to
  `OnServerEvent` is confirmed for editor-authored remotes.
- `FireClient(...arguments: any): nil` — exposed; delivery has not been
  established.
- `FireAllClients(...arguments: any): nil` — exposed; delivery has not been
  established.

## Events

- `OnServerEvent(senderId: number, ...arguments: any): Signal` — receives a
  numeric connection identifier, not a `Player` object.
- `OnClientEvent(...arguments: any): Signal` — exposed; delivery has not been
  established.

## Testing Notes

These observations are from Vortex Studio 0.3.3 and may differ in later
releases.

- Script-created remotes parented into `ReplicatedStorage` were visible to a
  client but did not dispatch to the server handler.
- `FireServer` rejects `Instance` values, including `LocalPlayer` and the
  character, with “Instances cannot be sent through a RemoteEvent yet”.
- The server-side `Players` service cannot currently resolve the numeric sender
  identifier to a Player, Character, or Humanoid.
