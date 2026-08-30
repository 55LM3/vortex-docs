---
title: Players
description: A container that holds all players currently connected as Player objects.
---

## Summary

A service representing connected clients as
[Player](https://create.playvortex.io/reference/classes/player/) instances.

### Example

```luau
-- LocalScript

local Players = game:GetService("Players")

local everyPlayer = Players:GetPlayers()
local player = Players.LocalPlayer
```

## Properties

- `Name` - the name of the service;
- `ClassName` - the runtime class name;
- `LocalPlayer` - available in a `LocalScript`; otherwise `nil`.

## Methods

- `GetPlayers(): { Player }` - returns the currently visible player list.

`GetChildren` is not exposed by the current Vortex Players service.

## Vortex Studio 0.3.3 notes

In a `LocalScript`, `GetPlayers()` returned the current player. In a server
`Script`, it remained an empty table across repeated polls, and no public
lookup route resolved the numeric sender ID received by a `RemoteEvent`.
