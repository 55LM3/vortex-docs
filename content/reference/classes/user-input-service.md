---
title: UserInputService
description: A client-only input service available through game:GetService.
---

## Summary

> [!NOTE]
> `UserInputService` is available through `game:GetService("UserInputService")`
> in `LocalScript`. It was not available in the tested `Script` context.

> [!WARNING]
> In the tested client runtime, two separate `game:GetService("UserInputService")`
> calls did not compare equal. Store a lookup result instead of relying on
> equality between separate lookups.

In the tested desktop client, `GamepadEnabled` and `TouchEnabled` were `false`,
while `KeyboardEnabled` and `MouseEnabled` were `true`.

<details>
<summary><b>Properties</b></summary>
Properties confirmed by runtime probes.
<br><br>

- [ClassName](#classname): `String`
- [GamepadEnabled](#gamepadenabled): `Boolean`
- [KeyboardEnabled](#keyboardenabled): `Boolean`
- [MouseEnabled](#mouseenabled): `Boolean`
- [Name](#name): `String`
- [TouchEnabled](#touchenabled): `Boolean`

</details>

<details>
<summary><b>Methods</b></summary>
Methods confirmed by runtime probes.
<br><br>

- [IsKeyDown(KeyCode: Enum.KeyCode)](#iskeydown): `Boolean`

</details>

<details>
<summary><b>Events</b></summary>
Signals confirmed by runtime probes.
<br><br>

- [InputBegan](#inputbegan): `Signal`

</details>

## Properties

### ClassName

> `String`
>
> The runtime class name of the service.

<br/>

### GamepadEnabled

> `Boolean`
>
> Whether gamepad input is enabled.

<br/>

### KeyboardEnabled

> `Boolean`
>
> Whether keyboard input is enabled.

<br/>

### MouseEnabled

> `Boolean`
>
> Whether mouse input is enabled.

<br/>

### Name

> `String`
>
> The service name shown by the runtime.

<br/>

### TouchEnabled

> `Boolean`
>
> Whether touch input is enabled.

<br/>

## Methods

### IsKeyDown

> `Boolean`
>
> `UserInputService:IsKeyDown(KeyCode: Enum.KeyCode)` returns whether the
> specified key is currently held. The method call and Boolean return value
> were verified in a `LocalScript`.

<br/>

## Events

### InputBegan

> `Signal`
>
> A connectable input signal. A live keyboard test delivered one callback per
> observed key press. Each callback received an input value whose `KeyCode`
> was the pressed `Enum.KeyCode` and whose `UserInputType` was
> `Enum.UserInputType.Keyboard`; `gameProcessedEvent` was `false` for the
> observed presses. Calling `IsKeyDown(input.KeyCode)` inside each callback
> succeeded and returned `true`. The connection disconnected successfully
> after the observation window.
>
> The interaction probe also prints `script.ClassName` and `script.Name`.
> Treat those values—not the runtime Output panel prefix—as the authoritative
> execution-context report.

<br/>
