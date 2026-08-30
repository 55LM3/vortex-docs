---
title: UserInputService
description: User Input Service is used to detect a players device, and also used to detect inputs from the Player.
---

## Methods

### IsKeyDown

Returns whether a certain key is being held down.

```
UserInputService:IsKeyDown(KeyCode: Enum.KeyCode): Boolean
```

#### Parameters

```
KeyCode: Enum.KeyCode
The Enum.KeyCode of the key
```

#### Returns

```
Boolean
Whether the specified key is being held down or not.
```

This method returns true if the specified key is held down, otherwise it returns false.

#### Examples

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

Fires whenever the Player interacts with an input device.

```
UserInputService.InputBegan(Input: InputObject, GameProcessedEvent: Boolean)
```

#### Parameters

```
Input: Input Object
An Input object which contains information about the user's input.
```

```
GameProcessedEvent: Boolean
Whether the Engine observed an action and acted on it. If a button was touched or clicked from this input, GameProcessedEvent will be true.
```

#### Examples

```luau
local UserInputService = game:GetService("UserInputService")

UserInputService.InputBegan:Connect(function(Input, GameProcessedEvent)
    if GameProcessedEvent then
        print("Game Processed Event")
    end

    if Input.KeyCode == Enum.KeyCode.R then
        print("R")
    end
end)
```

### InputEnded

Fires whenever the Player stops interacting with an input device.

```
UserInputService.InputEnded(Input: InputObject, GameProcessedEvent: Boolean)
```

#### Parameters

```
Input: Input Object
An Input object which contains information about the user's input.
```

```
GameProcessedEvent: Boolean
Whether the Engine observed an action and acted on it. If a button was touched or clicked from this input, GameProcessedEvent will be true.
```

#### Examples

```luau
local UserInputService = game:GetService("UserInputService")

UserInputService.InputEnded:Connect(function(Input, GameProcessedEvent)
    if GameProcessedEvent then
        print("Game Processed Event")
    end

    print("Input Ended.")
end)
```

## Vortex Studio 0.3.3 notes

The service and `InputBegan` are confirmed in a `LocalScript`; a normal server
`Script` has no UserInputService. `InputEnded` is exposed in a LocalScript, but
its delivery has not yet been independently established. `InputChanged`,
`GetMouseLocation`, `MouseBehavior`, and `MouseIconEnabled` are currently not
exposed.
