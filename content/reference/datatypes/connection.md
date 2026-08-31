---
title: Connections
description: A variable that returns the connection between an event to a function.
---

## Example
In this example, the player has three attempts to open a door by pressing `E`. The script checks for when the keybind is pressed, and once the player has run out of attempts, the connection is disconnected and the game stops listening for key presses.

## Client Script
- placed in `StarterPlayerScripts`
```lua
local UserInputService = game:GetService("UserInputService")
local ReplicatedStorage = game:GetService("ReplicatedStorage")

local openDoor = ReplicatedStorage.OpenDoor

local attempts = 0
local connection = nil

connection = UserInputService.InputBegan:Connect(function(input)
    if input.KeyCode == Enum.KeyCode.E then
        if attempts == 3 then
            connection:Disconnect()
            return
        end
        openDoor:FireServer()
        attempts += 1
    end
end)
```

## Methods
| Method | Returns | Description |
|---|---|---|
| `Disconnect()` | void | Stops the connection from firing and permanently detaches it from the event. |

## Events
A `Connection` has no events of its own. It's returned by calling `:Connect()` on an event.
