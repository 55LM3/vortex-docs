---
title: Humanoid
description: Represents the humanoid controller in a Player Character.
---

The current player's humanoid is available as
`game:GetService("Players").LocalPlayer.Character.Humanoid` in a `LocalScript`.

## Summary

<details>
<summary><b>Properties</b></summary>
Properties of a `Humanoid`.
<br><br>

* [ClassName](#classname): `String`
* [Name](#name): `String`
* [Health](#health): `Number`
* [MaxHealth](#maxhealth): `Number`

</details>

<details>
<summary><b>Methods</b></summary>
Methods of a `Humanoid`.
<br><br>

* [IsDead](#isdead): `Boolean`

</details>

<details>
<summary><b>Signals</b></summary>
Signals of a `Humanoid`.
<br><br>

* [Died](#died): [`Signal`](/content/reference/datatypes/signal.md)
* [HealthChanged](#healthchanged): [`Signal`](/content/reference/datatypes/signal.md)

</details>

## Properties

### ClassName

> `String`
>
> The Humanoid class name, `"Humanoid"`.

<br/>

### Name

> `String`
>
> The Humanoid name.

<br/>

### Health

> `Number`
>
> The current health value.

<br/>

### MaxHealth

> `Number`
>
> The maximum health value.

<br/>

## Methods

### IsDead

> `Boolean`
>
> `humanoid:IsDead()`
>
> Returns whether the Humanoid is dead.

## Signals

### Died

> [`Signal`](/content/reference/datatypes/signal.md)
>
> `humanoid.Died`
>
> Signals that the Humanoid died.

<br/>

### HealthChanged

> [`Signal`](/content/reference/datatypes/signal.md)
>
> `humanoid.HealthChanged`
>
> Signals that the Humanoid health changed.

#### Parameters

- `health`: `Number` — the updated health value.

## Testing Notes

These observations are from Vortex Studio 0.3.3, the current public build, and
may differ in later releases.

The observed character Humanoid was a specialized table with `ClassName` and
`Name` both reporting `"Humanoid"`, and `Health` and `MaxHealth` both
reporting `100`. `IsDead()` was exposed and returned `false`. `Died` and
`HealthChanged` exposed `Signal:Connect`.

In a `LocalScript`, assigning `Health` is rejected: it is read-only there and
server-authoritative. `Died` and `HealthChanged` are exposed Signal references,
but their delivery could not be tested because no reliable server-side
player/Humanoid binding was available.

The specialized Humanoid has an opaque `__index` and `__newindex` metatable;
`IsA` was not exposed on the value itself.
