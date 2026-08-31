---
title: Remote Functions
description: Two-way communication between the server and clients, with a return value.
---

# Remote Functions
A `RemoteFunction` calls between the server and clients and waits for a response. Unlike a `RemoteEvent`, it yields the calling script until the other side returns a value. For firing one-way communication signals that don't need a response, use [RemoteEvent](/guides/remote-events/) instead.

The primary parent container for remote functions is `ReplicatedStorage`, as both the server and client can see and access it.
> ⚠ **Security note:** never trust arguments a client sends via `InvokeServer` at
> face value - a modified client can call it with anything. Re-validate
> any arguments on the server before acting on it.

## Example
In this example, pressing `E` sends a signal to the server to ask whether a door is locked. The locked state only exists as a variable inside the server script, so the client has to ask the server through a `RemoteFunction`.

## Server Script
- placed in `ServerScriptService`
- be sure to create an `RemoteFunction` named `IsDoorLocked` parented to `ReplicatedStorage`
```lua
local ReplicatedStorage = game:GetService("ReplicatedStorage")

local isDoorLocked = ReplicatedStorage.IsDoorLocked
local doorLocked = true

isDoorLocked.OnServerInvoke = function(player)
    return doorLocked
end
```

## Client Script
- placed in `StarterPlayerScripts`
```lua
local ReplicatedStorage = game:GetService("ReplicatedStorage")
local UserInputService = game:GetService("UserInputService")

local isDoorLocked = ReplicatedStorage.IsDoorLocked

UserInputService.InputBegan:Connect(function(input)
    if input.KeyCode == Enum.KeyCode.E then
        local locked = isDoorLocked:InvokeServer()
        print(locked and "The door is locked" or "The door is unlocked")
    end
end)
```

## Methods

| Method | Returns | Description |
|---|---|---|
| `InvokeServer(...)` | any | Called from a client. Sends arguments to the server and yields until it returns a value. |
| `InvokeClient(player, ...)` | any | Called from the server. Sends arguments to chosen client and yields until it returns a value. |

## Events
This class has no events. Instead, assign a function directly to `OnServerInvoke` (server) or `OnClientInvoke` (client) to handle incoming calls.
