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
- `Character` - the current [`Character`](./character.md) `Model`, when available.
- `Position`, `Rotation`, and `CFrame` - initially `nil`, writable
  Player-local projection fields in the tested runtime. They are not aliases
  for the public character root's physical transform.
- `Orientation` - a writable [`Vector3`](../datatypes/vector3.md) rotation
  value. This field is initially `nil` in the tested projection.

## Rotation

`Player.Orientation` is the only verified character-rotation route in Vortex
Studio 0.3.4. Assigning `Vector3.new(0, 90, 0)` from a server Script stored the
value and visibly quarter-turned the Player character. The same assignment in
a LocalScript also stored and read back successfully; its replication and
visibility outside that LocalScript have not yet been tested.

```luau
player.Orientation = Vector3.new(0, 90, 0)
```

This is distinct from the Character and root-part projections: their tested
orientation writes are discarded or rejected. See
[Character](./character.md) and
[HumanoidRootPart](./humanoid-root-part.md).

## Transform projection fields

`Player.Position`, `Player.Rotation`, and `Player.CFrame` begin as `nil` but
accept and retain assigned `Vector3`/`CFrame` values in both a server Script
and a LocalScript. They do not update the public
`Character.HumanoidRootPart`: an explicit three-stud `Player.Position` write
left the root at its original position in both contexts, and a
`Player.Rotation` write likewise caused no translation.

`Position` and `Rotation` are also context-local. A 15-second server writer /
LocalScript observer run, followed by the contexts swapped, showed that each
writer retained its own values while the observer stayed `nil`. Do not use
these fields for character movement, replicated state, or a server-client
metadata channel.

`Player.Orientation` is separate from this result: its server-side visual
rotation effect is verified above, but its replication behavior has not yet
been tested.

## Methods and signals

The 0.3.4 Player surface probe did not expose any of the tested standard Player
or Instance methods, nor any tested lifecycle, chat, hierarchy, or change
signals. This includes `GetChildren`, attributes, `GetMouse`, `Kick`, and
`LoadCharacter`.

A dedicated 15-second observer also found `Player.CharacterAdded` to be `nil`
in both a LocalScript and a server Script throughout its full window. The
delayed and replaced visual Character Scene therefore does not correspond to
an exposed Player character-lifecycle signal.

## Observed character projection

The following is the confirmed, directly accessible portion of a player's
runtime character projection in Vortex Studio 0.3.4:

```text
Player
└── Character (Model)
    ├── Humanoid
    └── HumanoidRootPart (Part projection)
```

[`Character`](./character.md), [`Humanoid`](./humanoid.md), and
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
