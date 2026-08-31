---
title: Instance.new
description: Creates a new Instance of the given class
---

<!-- 
Instance.new
Revision 1

Written by Arbuzyonak on August 30th, 2026
-->

## Summary

<details>
<summary><b>Syntax</b></summary>

`Instance.new(className: string, parent: Instance?): Instance`

</details>

## Overview

`Instance.new` creates a new [`Instance`](../classes/instance.md) of the class passed as `className`.

```lua
local part = Instance.new("Part")
print(part)            --> Part
print(part.ClassName)  --> Part
print(part.Name)       --> Part
```

## Parenting

A new instance has no parent: it exists in memory, but it is not rendered, replicated, or saved until you assign its [`Parent`](../classes/instance.md).

Set the parent **last**, after configuring the instance, so scripts listening for new objects receive it fully configured:

```lua
local part = Instance.new("Part")
part.Name = "Platform"
part.Size = Vector3.new(8, 1, 8)
part.Position = Vector3.new(0, 10, 0)
part.Anchored = true
part.Parent = workspace
```
Or, you can optionally set the parent in the second argument when calling **Instance.new**

```lua
local part = Instance.new("Part", workspace)
part.Name = "Platform"
part.Size = Vector3.new(8, 1, 8)
part.Position = Vector3.new(0, 10, 0)
part.Anchored = true
-- NOT NEEDED: part.Parent = workspace
```
If no parent is passed in, nor set later, the Instance's parent defaults to **workspace**

## Default state

> A freshly created `Part` is unanchored, medium gray, and positioned at the world origin (`0, 0.5, 0`), with its [`Name`](#overview) defaulting to the class name. Any property you do not set yourself holds the class default.

## Notes

- Common creatable classes include [`Part`](../classes/part.md), [`Model`](../classes/model.md), [`Folder`](../classes/folder.md), [`SpawnLocation`](../classes/spawnlocation.md), [`Script`](../classes/script.md), [`LocalScript`](../classes/localscript.md), [`ModuleScript`](../classes/modulescript.md), [`IntValue`](../classes/int-value.md), [`StringValue`](../classes/string-value.md), [`BindableEvent`](../classes/bindable-event.md), [`RemoteEvent`](../classes/remote-event.md), [`RemoteFunction`](../classes/remote-function.md), [`PointLight`](../classes/point-light.md), and [`SpotLight`](../classes/spot-light.md).

<br/>
