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

The tested Vortex runtime exposed no callable methods or connectable signals.

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
