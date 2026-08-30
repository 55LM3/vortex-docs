---
title: UserInputService
description: User Input Service is used to detect a players device, and also used to detect inputs from the Player.
---

## Methods
### IsKeyDown
Returns whether a certain is being held down.

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
This method returns true if they are holding down the specified key, otherwise it returns false.
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
UserInputService.InputBegan(Input: InpitObject, GameProcessedEvent: Boolean)
```

#### Parameters
```
Input: Input Object
An Input object which contains information about the users input.
```
```
GameProcessedEvent: Boolean
Whether the Engine observed an action and acted on it. If a button was touched or clicked from this input, GameProcessedEvent will be true.
```

#### Returns

#### Examples
```luau
local UserInputService = game:GetService("UserInputService")

UserInputService.InputBegan:Connect(function(Input, GameProccessedEvent)
    if GameProccessedEvent then
       print("Game Proccessed Event")
    end
    
    if Input.KeyCode == Enum.KeyCode.R then
        print("R")
    end
end)
```
