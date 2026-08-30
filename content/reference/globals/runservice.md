---
title: RunService
description: Responsible for all activities that happen during runtime.
---
<!-- 
RunService
Starting info

AlmostGalactic
-->

# Getting the Service
```lua
local RunService = game:GetService("RunService")
```

## Methods
 - Heartbeat (deltaTime: number?)


## Examples & How to Use

### Heartbeat
```lua
local RunService = game:GetService("RunService") -- acquire the service

function beat(deltaTime: number)
  print(deltaTime)
end

RunService.Heartbeat:Connect(beat)
```
