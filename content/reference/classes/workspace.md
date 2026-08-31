---
title: Workspace
description: Service that holds and renders every 3D player-interactable instance.
---

<!-- 
Instance
Revision 1.1

Written by TheJustDare on August 31th, 2026
-->

## Summary

<details>
<summary><b>Properties</b></summary>

Properties of `Workspace`
<br>

* [Name](#name): `String`
* [ClassName](#className): `String`

</details>

<details>
<summary><b>Methods</b></summary>

Methods of `Workspace`
<br>

* [FindFirstChild()](#findFirstChild): `Instance?`
* [GetChildren()](#getchildren): `{ Instance }`
* [WaitForChild()](#waitForChild): `Instance`

</details>

## Properties

### Name

The name of the [Workspace](/content/reference/classes/workspace.md). \
This property is read only and cannot be changed.

<br>

### ClassName

The class name of the [Workspace](/content/reference/classes/workspace.md). \
This property is read only and cannot be changed.

<br>

## Methods

### FindFirstChild()

Returns the first child found with the given name. \
For `FindFirstChild()` to work, a name of a type of `string` has to be passed. \
Optionally a second argument can be given, whether to search for the `Instance` recursively.

#### Syntax
`Instance:FindFirstChild(name: string, recursive: boolean): Instance?`

```lua
local part = workspace:FindFirstChild("Part")

if part then
    part.Position = Vector3.new(3, 1, 4)
end
```

<br>

### GetChildren()

Returns an array with all children of the [Instance](/content//reference/classes/instance.md).

#### Syntax
`Instance:GetChildren(): { Instance }`

```lua
local model = workspace.Model
local parts = model:GetChildren()

for i, part in parts do
    print(part.Name .. " is child number " .. i)
end
```

<br/>

### WaitForChild()

Returns the child of the [Instance](/content//reference/classes/instance.md) with the given name. \
The current thread will yield if the child does not exist, until it does.

#### Syntax
`Instance:WaitForChild(name: string, timeOut: number): Instance`

```lua
local block = workspace:WaitForChild("Block")
print(block .. " was added to the Workspace")
```
