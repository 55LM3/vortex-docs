---
title: Game
description: The root instance of a game.
---

<!-- 
Game
Revision 1

Written by Kindtracker on August 29th, 2026

---

Revision 2 - ReplicatedStorage and ServerScriptService

Written by LumiMakesStuff (lumi on Vortex) August 30th, 2026
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

* [Workspace](../classes/workspace.md)
* [Players](../classes/players.md)
* [ReplicatedStorage](../classes/replicated-storage.md)
* [StarterPlayerScripts](../classes/starter-player-scripts.md)
* [ServerScriptService](../classes/server-script-service.md)
* [Lighting](../classes/lighting.md)

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
> 
> The Workspace is the root object that holds anything that is currently in the world. [Workspace](../classes/workspace.md)

<br/>

### Players

> `Instance`
>
> Stub. [Players](../classes/players.md)

<br/>

### ReplicatedStorage

> `Instance`
>
> ReplicatedStorage contains objects replicated to the Client and Server. When the Server makes a modification, this is replicated to all clients. Any changes made by clients are not replicated to the server. [ReplicatedStorage](../classes/replicated-storage.md)

<br/>

### StarterPlayerScripts

> `Instance`
>
> Stub. [StarterPlayerScripts](../classes/starter-player-scripts.md)

<br/>

### ServerScriptService

> `Instance`
>
> ServerScriptService contains [Scripts](../classes/script.md) that run when the server starts. [ServerScriptService](../classes/server-script-service.md)

<br/>

### Lighting

> `Instance`
>
> Lighting is the game service that controls basic rendering and atmospherics. [Lighting](../classes/lighting.md)

<br/>
