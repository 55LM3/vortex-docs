---
title: IntValue
description: Stub
---

Stores an Integer value 

# Summary
[IntValues](https://create.playvortex.io/reference/classes/int-value/) are a very simple way to store an integer outside of a script. You can get/set it's stored integer with `IntValue.Value`.

# Properties

## .Name
  `String` 
  
The name of the [IntValue](https://create.playvortex.io/reference/classes/int-value/) , and label in the explorer.

## .Value
`Integer`

The `Integer` Stored inside [IntValue](https://create.playvortex.io/reference/classes/int-value/)

# Code Snippet

    local newVal = Instance.new("IntValue")
    newVal.Parent = game.Workspace

	newVal.Value = 9999

	print(newVal.Value)

## Expected Output

    9999