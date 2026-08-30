---
title: Players
description: A container that holds all players currently connected as Player objects.
---

## Summary

<details>
<summary><b>Properties</b></summary>
<br>

- [ClassName](#classname): `String`
- [LocalPlayer](#localplayer): [`Player`](/content/reference/classes/player.md) | `nil`
- [Name](#name): `String`

</details>

<details>
<summary><b>Methods</b></summary>
<br>

- [GetPlayers](#getplayers): `{ Player }`

</details>

## Properties

### ClassName
> `String` \
\
The runtime class name of the service.

<br/>


### LocalPlayer
> [`Player`](/content/reference/classes/player.md) | `nil` \
\
The `Player` for the local client, or `nil` when no local player is available.

<br/>


### Name
> `String` \
\
The service name shown by the runtime.

<br/>

## Methods

### GetPlayers()
> `{ Player }` \
\
Returns a table containing the currently connected players.

<br/>

## Testing Notes

These observations are from Vortex Studio 0.3.3, the current public build, and
may differ in later releases.

`LocalScripts` returned only the current player. `Scripts` returned no players.
