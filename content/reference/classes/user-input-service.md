---
title: UserInputService
description: A service that allows access to player input
---

<!--
Debris
Revision 1

Written by MtcLuna05 on August 30th, 2026
-->

## Summary

> [!NOTE]
> `UserInputService` is only callable in LocalScripts.\
> Two separate `game:GetService("UserInputService")` calls do not return the same result.

<details>
<summary><b>Properties</b></summary>

- [ClassName](#classname): `String`
- [GamepadEnabled](#gamepadenabled): `Boolean`
- [KeyboardEnabled](#keyboardenabled): `Boolean`
- [MouseEnabled](#mouseenabled): `Boolean`
- [Name](#name): `String`
- [TouchEnabled](#touchenabled): `Boolean`

</details>

<details>
<summary><b>Methods</b></summary>

- [IsKeyDown(KeyCode: Enum.KeyCode)](#iskeydown): `Boolean`

</details>

<details>
<summary><b>Events</b></summary>

- [InputBegan](#inputbegan): `Signal`

</details>

## Properties

### ClassName

> `String`
>
> The runtime class name of the service.

### GamepadEnabled

> `Boolean`
>
> Whether gamepad input is enabled.

### KeyboardEnabled

> `Boolean`
>
> Whether keyboard input is enabled.

### MouseEnabled

> `Boolean`
>
> Whether mouse input is enabled.

### Name

> `String`
>
> The service name shown by the runtime.

### TouchEnabled

> `Boolean`
>
> Whether touch input is enabled.

## Methods

### IsKeyDown

> `Boolean`
>
> `UserInputService:IsKeyDown(KeyCode: Enum.KeyCode)` returns whether the
> specified key is currently held.

## Events

### InputBegan

> `Signal`
>
> A connectable input signal.\
> Called once per key press. Each callback received an input value whose `KeyCode`
> was the pressed `Enum.KeyCode` and whose `UserInputType` depends on the used peripheric.\
> Calling `IsKeyDown(input.KeyCode)` inside each callback
> succeeded and returned `true`.
