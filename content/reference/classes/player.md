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

`GetChildren` is not exposed on the current Vortex `Player` projection.

## Vortex Studio 0.3.3 notes

`Players.LocalPlayer` is available in a `LocalScript` and `nil` in a normal
server `Script`. The observed `Character` is a `Model` named after the player;
its `Humanoid` and `HumanoidRootPart` are directly readable.
