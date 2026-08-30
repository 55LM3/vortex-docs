---
title: Player
description: Holds information about a connected client.
---

The current client player is available as `game:GetService("Players").LocalPlayer`
in a `LocalScript`.

## Summary

<details>
<summary><b>Properties</b></summary>
Properties of a `Player`.
<br><br>

* [Character](#character): [`Model`](/content/reference/classes/model.md)
* [ClassName](#classname): `String`
* [Name](#name): `String`

</details>

## Properties

### Character

> [`Model`](/content/reference/classes/model.md)
>
> The Player's current character model.

<br/>

### ClassName

> `String`
>
> The Player's class name, `"Player"`.

<br/>

### Name

> `String`
>
> The Player's name.

## Testing Notes

These observations are from Vortex Studio 0.3.3, the current public build, and
may differ in later releases.

`Players.LocalPlayer` is available in a `LocalScript` and is `nil` in a
`Script`.

The observed `Character` was a `Model` named after the player. Its `Humanoid`
and `HumanoidRootPart` were directly readable and matched
`character:FindFirstChild("Humanoid")` and
`character:FindFirstChild("HumanoidRootPart")` respectively.
