---
title: Workspace
description: Service that holds every visible (or invisible) player-interactible instance.
---

<!-- 
Workspace

Written by Prouddani on August 29th, 2026
-->

## Summary

Service that holds every player-interactible instance. Consequently, making them the only service as of now whose children can be viewed by the player.
<br>
Additionally, can be used to raycast.

<details>
<summary><b>Properties</b></summary>
Properties of a Workspace, in the order they appear on Vortex Studio
<br><br>

- [ClassName](#classname): `String`
- [Name](#name): `String`
</details>

<details>
<summary><b>Methods</b></summary>
Methods of a `Workspace`.
<br><br>

- [FindFirstChild](#findfirstchild): [`Instance`](/content/reference/classes/instance.md) | `nil`
- [GetChildren](#getchildren): `{ Instance }`
- [WaitForChild](#waitforchild): [`Instance`](/content/reference/classes/instance.md)

</details>

## Properties

### ClassName
> `String` \
\
The runtime class name of the service.

<br/>


### Name
> `String` \
\
The service name shown by the runtime.

<br/>

## Methods

### FindFirstChild()
> [`Instance`](/content/reference/classes/instance.md) | `nil` \
\
`workspace:FindFirstChild(name: String)` \
\
Returns the first direct child with the supplied `name`, or `nil` when none is
found.

#### Parameters

- `name`: `String` — the child name to find.

<br/>


### GetChildren()
> `{ Instance }` \
\
Returns the direct children of `Workspace`.

<br/>


### WaitForChild()
> [`Instance`](/content/reference/classes/instance.md) \
\
`workspace:WaitForChild(name: String)` \
\
Waits for and returns a direct child with the supplied `name`.

#### Parameters

- `name`: `String` — the child name to wait for.


<br/>

## Testing Notes

These observations are from Vortex Studio 0.3.3, the current public build, and
may differ in later releases.

`Raycast` was not exposed. A temporary `Part` can be parented to `Workspace`,
and `WaitForChild` resolves it. `FindFirstChild` returns `nil` and
`GetChildren` omits it.
