---
title: Game
description: The root instance of a game.
---

<!-- 
Game
Revision 1

Written by Kindtracker on August 29th, 2026
-->

> [!NOTE]
> There will be more things (methods, constructors, properties, etc.) in the future. This is based on leaks.

`game` is the root instance and provides access to services.

## Summary

<details>
<summary><b>Methods</b></summary>
Methods of `game`.
<br><br>

* [GetService(serviceName: `String`)](#getservice): `Instance`

</details>

<details>
<summary><b>Services</b></summary>
Services of `game`.
<br><br>

* [Workspace](/content/reference/classes/workspace.md)
* [Players](/content/reference/classes/players.md)
* [ReplicatedStorage](/content/reference/classes/replicated-storage.md)
* [StarterPlayerScripts](/content/reference/classes/starter-player-scripts.md)
* [ServerScriptService](/content/reference/classes/server-script-service.md)
* [Lighting](/content/reference/classes/lighting.md)
* [Debris](/content/reference/classes/debris.md)
* [RunService](/content/reference/classes/run-service.md)
* [TweenService](/content/reference/classes/tween-service.md)
* [UserInputService](/content/reference/classes/user-input-service.md)

</details>

## Methods

### GetService(serviceName: `String`)

> `Instance`
>
> Returns the service with specified name.

<br/>

## Verified runtime compatibility

`game:GetService("Workspace")` accepted its service-name parameter and
returned a `Workspace` named `Workspace` in both tested execution contexts.
The readable `game.Workspace` property reported the same class and name.

### Properties

- `Workspace` — readable property on `game`.

### Callbacks

- `OnClose` — initially `nil` in both tested contexts, assignable to a
  function, and restorable to its original value. The probe does not invoke
  the callback.

### Service lookup identity

In the tested runtime, two `game:GetService` calls for each of `Workspace`,
`Players`, `ReplicatedStorage`, `StarterPlayerScripts`, `ServerScriptService`,
and the client-only `UserInputService` did **not** compare equal. Store a
lookup result instead of using repeated-lookup identity comparisons. `Debris`,
`RunService`, and `TweenService` did compare equal across repeated lookups.

### Service discovery coverage

The discovery probe attempted `game:GetService` with 160 candidate service
names. It found nine services in `LocalScript` and eight in `Script`:
`Workspace`, `Players`, `ReplicatedStorage`, `StarterPlayerScripts`,
`ServerScriptService`, `Debris`, `RunService`, and `TweenService` in both
contexts, plus `UserInputService` in `LocalScript`. `Lighting` was not
available in either context. This is a candidate sweep, not a public service
enumeration API.

### Broad member-probe coverage

The following counts describe the documented members checked by the broad
property and method probes. They are coverage metrics, not a complete API
inventory.

| Value | Properties | Methods |
| --- | ---: | ---: |
| `game` | 1/25 | 1/36 |
| `Workspace` | 2/69 | 3/72 |
| `Part` | 12/82 | 13/63 |
| `Instance` (tested through Part) | 2/10 | 2/2 |
| `Players` | 3/20 in LocalScript; 2/20 in Script | 0/34 |
| `ReplicatedStorage` | 2/10 | 3/34 |
| `StarterPlayerScripts` | 2/10 | 3/34 |
| `ServerScriptService` | 2/11 | 3/34 |
| `Debris` | 0/11 | 0/34 |
| `RunService` | 0/12 | 0/34 |
| `TweenService` | 0/10 | 0/34 |
| `UserInputService` | 6/29 in LocalScript; unavailable in Script | 0/34 |

Some focused probes subsequently verified members not included in those broad
lists, including `Players:GetPlayers` and `UserInputService:IsKeyDown`.

## Services

### Workspace

> `Instance`
> The Workspace is the root object that holds anything that is currently in the world. [Workspace](/content/reference/classes/workspace.md)

<br/>

### Players

> `Instance`
>
> Stub. [Players](/content/reference/classes/players.md)

<br/>

### ReplicatedStorage

> `Instance`
>
> Stub. [ReplicatedStorage](/content/reference/classes/replicated-storage.md)

<br/>

### StarterPlayerScripts

> `Instance`
>
> Stub. [StarterPlayerScripts](/content/reference/classes/starter-player-scripts.md)

<br/>

### ServerScriptService

> `Instance`
>
> Stub. [ServerScriptService](/content/reference/classes/server-script-service.md)

<br/>

### Lighting

> `Instance`
>
> lighting is the game service that controls basic rendering and atmospherics. [Lighting](/content/reference/classes/lighting.md)

<br/>

### Debris

> `Instance`
>
> Available through `game:GetService("Debris")` in both `Script` and `LocalScript`. [Debris](/content/reference/classes/debris.md)

<br/>

### RunService

> `Instance`
>
> Available through `game:GetService("RunService")` in both `Script` and `LocalScript`. [RunService](/content/reference/classes/run-service.md)

<br/>

### TweenService

> `Instance`
>
> Available through `game:GetService("TweenService")` in both `Script` and `LocalScript`. [TweenService](/content/reference/classes/tween-service.md)

<br/>

### UserInputService

> `Instance`
>
> Available through `game:GetService("UserInputService")` in `LocalScript`. It was not available in the tested `Script` context. In the tested client runtime, repeated lookups did not compare equal. [UserInputService](/content/reference/classes/user-input-service.md)

<br/>
