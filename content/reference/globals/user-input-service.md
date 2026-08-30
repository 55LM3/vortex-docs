---
title: UserInputService
description: A service that provides access to player input.
---

## Summary

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

- [IsKeyDown](#iskeydown): `Boolean`

</details>

<details>
<summary><b>Events</b></summary>

- [InputBegan](#inputbegan): [`Signal`](/content/reference/datatypes/signal.md)

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

### IsKeyDown()

```luau
UserInputService:IsKeyDown(keyCode: Enum.KeyCode): boolean
```

Returns whether the key corresponding to the `keyCode` is currently held down.

#### Parameters

- `keyCode`: `Enum.KeyCode` — the key to inspect.

```luau
local UserInputService = game:GetService("UserInputService")

UserInputService.InputBegan:Connect(function()
    if UserInputService:IsKeyDown(Enum.KeyCode.LeftShift) then
        print("Left Shift")
    end
end)
```

## Events

### InputBegan

```luau
UserInputService.InputBegan(input: InputObject, gameProcessedEvent: boolean)
```

Fires once per key press, regardless of the key. `input` contains details about the input, including
`KeyCode` and `UserInputType`, which depends on the input device used.
`gameProcessedEvent` is `true` when the engine has already handled the input.
`IsKeyDown(input.KeyCode)` returns `true` if called inside the event

#### Parameters

- `input`: [`InputObject`](/content/reference/datatypes/input-object.md) — details about the input that fired the event.
- `gameProcessedEvent`: `Boolean` — whether the engine already handled the input.

```luau
local UserInputService = game:GetService("UserInputService")

UserInputService.InputBegan:Connect(function(input, gameProcessedEvent)
    if gameProcessedEvent then
        print("Game Processed Event")
        return
    end

    if input.KeyCode == Enum.KeyCode.R then
        print("R")
    end
end)
```

## Testing Notes

These observations are from Vortex Studio 0.3.3, the current public build, and
may differ in later releases.

`UserInputService` is available to `LocalScripts`; retrieving it from a
`Script` returns no service. During `InputBegan`, keyboard input provides a
`KeyCode` and `UserInputType.Keyboard`, and `IsKeyDown(input.KeyCode)` returns
`true` while the key is held.
