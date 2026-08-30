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
