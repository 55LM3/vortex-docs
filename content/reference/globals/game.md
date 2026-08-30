---
title: Game
description: The root instance of a game.
---

<!-- 
Game
Revision 2

Written by Kindtracker on August 29th, 2026
Edited by MtcLuna05 on August 30th, 2026
-->

> [!NOTE]
> There will be more things (methods, constructors, properties, etc.) in the future.

`game` is the root instance and provides access to services.

## Summary

<details>
<summary><b>Properties</b></summary>
Properties of `game`.
<br><br>

* [Workspace](#workspace): [`Workspace`](/content/reference/classes/workspace.md)

</details>

<details>
<summary><b>Methods</b></summary>
Methods of `game`.
<br><br>

* [GetService(serviceName: `String`)](#getservice): `Instance`

</details>

<details>
<summary><b>Callbacks</b></summary>
Callbacks of `game`.
<br><br>

* [OnClose](#onclose): `Function` | `nil`

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
* [UserInputService](/content/reference/globals/user-input-service.md)

</details>

## Properties

### Workspace

> [`Workspace`](/content/reference/classes/workspace.md)
>
> The root `Workspace` service.

<br/>

## Methods

### GetService()

> `Instance`
>
> `game:GetService(serviceName: String)`
>
> Returns the service with the specified name.

#### Parameters

- `serviceName`: `String` — the name of the service to retrieve.

<br/>

## Callbacks

### OnClose

> `Function` | `nil`
>
> An optional callback that can be assigned before the game closes.

<br/>

## Services

### Workspace

> `Instance`
>
> The Workspace is the root object that holds anything that is currently in the world. [Workspace](/content/reference/classes/workspace.md)

<br/>

### Players

> `Instance`
>
> The service that contains the currently connected player objects.
> [Players](/content/reference/classes/players.md)

<br/>

### ReplicatedStorage

> `Instance`
>
> A container for instances loaded by both the server and the client.
> [ReplicatedStorage](/content/reference/classes/replicated-storage.md)

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

## Testing Notes

These observations are from Vortex Studio 0.3.3, the current public build, and
may differ in later releases.

`game.Workspace` and `game:GetService("Workspace")` both report `ClassName`
and `Name` as `Workspace`. `game.OnClose` starts as `nil`; assigning a
function succeeds, but callback delivery has not been established.
