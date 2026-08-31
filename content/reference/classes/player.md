---
title: Player
description: An instance holding information about a connected client.
---

## Summary

Represents a connected client. The current client is available through the
[Players](https://create.playvortex.io/reference/classes/players/) service as
`LocalPlayer`.

### Example

```luau
-- LocalScript

local Players = game:GetService("Players")
local player = Players.LocalPlayer

print("Hello, " .. player.Name .. "!")
```

## Properties

- `Name` - the player's name;
- `ClassName` - `"Player"` for the current client projection;
- `Character` - the current character `Model`, when available;
- `Parent` - reads as `nil` for the observed `LocalPlayer`. Assigning it is
  client-local and does not insert the Player into Workspace hierarchy queries.

## Methods

`GetChildren` is not exposed on the current Vortex `Player` projection. It also
does not expose the Instance attribute methods `GetAttribute`, `GetAttributes`,
`SetAttribute`, or `GetAttributeChangedSignal`.

## Vortex Studio 0.3.4 notes

`Players.LocalPlayer` is available in a `LocalScript` and `nil` in a normal
server `Script`. The observed `Character` is a `Model` named after the player;
its `Humanoid` and `HumanoidRootPart` are directly readable. A server Script
can now obtain this Player through `Players:GetPlayers()`, but it cannot yet
derive the Player from a RemoteEvent's numeric sender id.

The client `LocalPlayer` and the server-visible Player both lack the Instance
attribute method surface. Player attributes therefore cannot be used as a
server-to-client metadata channel in the tested runtime.
