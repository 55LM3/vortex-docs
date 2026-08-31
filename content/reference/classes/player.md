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
- `Character` - the current character `Model`, when available.

## Methods and signals

The 0.3.4 Player surface probe did not expose any of the tested standard Player
or Instance methods, nor any tested lifecycle, chat, hierarchy, or change
signals. This includes `GetChildren`, attributes, `GetMouse`, `Kick`, and
`LoadCharacter`.

## Observed character projection

The following is the confirmed, directly accessible portion of a player's
runtime character projection in Vortex Studio 0.3.4:

```text
Player
└── Character (Model)
    ├── Humanoid
    └── HumanoidRootPart (Part projection)
```

`Character`, [`Humanoid`](./humanoid.md), and
[`HumanoidRootPart`](./humanoid-root-part.md) are direct readable members—not
a `Player:GetChildren()` result. `Character:FindFirstChild` resolves the same
Humanoid and root-part values. `Character:GetChildren()` instead returns one
unnamed generic `Instance`, so it is not a usable character-rig inventory.
The other tested standard R6/R15 body-part and `Animate` names were absent
from the public Character projection. The anonymous child can later expose a
separate, transient visual `Scene` containing the rendered rig and
avatar-specific attachments; see [Model: Transient Character visual
Scene](./model.md#transient-character-visual-scene).

## Vortex Studio 0.3.4 notes

`Players.LocalPlayer` is available in a `LocalScript` and `nil` in a normal
server `Script`. In both contexts, the Player surface probe found only
`ClassName`, `Name`, and `Character` as non-`nil` fields. `Parent` reads as
`nil` for the observed LocalPlayer. A server Script can obtain this Player
through `Players:GetPlayers()`, but it cannot derive the Player from a
RemoteEvent's numeric sender id.

The client `LocalPlayer` and the server-visible Player both lack the Instance
attribute method surface. Player attributes therefore cannot be used as a
server-to-client metadata channel in the tested runtime.
