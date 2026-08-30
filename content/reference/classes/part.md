---
title: Part
description: A primitive rectangular prism
---

<!-- 
Part
Revision 1

Written by KingTasaz on August 28th, 2026
-->

## Summary

<details>
<summary><b>Properties</b></summary>
Properties of a Part, in the order they appear on Vortex Studio.
<br><br>
<ul>
<details>
<summary><b>Appearance</b></summary>

- [Color](#color): [`Color3`](/content/reference/datatypes/color3.md)
- [Transparency](#transparency): `Float`
- [Material](#material): [`Enum.Material`](/content/reference/datatypes/enumitem.md) <!-- not sure if this should link to enumitem.md or enum.md -->
- [Cast Shadow](#cast-shadow): `Boolean`

</details>

<details>
<summary><b>Behaviour</b></summary>

- [Anchored](#anchored): `Boolean`
- [CanCollide](#cancollide): `Boolean`
- [Truss](#truss): `Boolean`

</details>

<details>
<summary><b>Transform</b></summary>

- [Name](#name): `String`
- [Position](#position): [`Vector3`](/content/reference/datatypes/vector3.md)
- [Rotation](#rotation): [`Vector3`](/content/reference/datatypes/vector3.md)
- [Size](#size): [`Vector3`](/content/reference/datatypes/vector3.md)

</details>

</ul>
</details>

<!-- In the future, there can be more lists of `features`(?) that a part has, such as events or functions/methods -->

## Properties

### Anchored
> `Boolean` \
\
When `true`, the given part will be unable to move via interactions with the environment. \
When `false`, the part will experience gravity and forces from other parts.

<br/>


### CanCollide
> `Boolean` \
\
Determines whether the `part` is given physics collisions, or whether it can phase through other parts. \
\
**Note:** A `part` cannot be unanchored while collision is disabled.

<br/>


### Cast Shadow
> `Boolean` \
\
Controls whether or not the `part` will cast a shadow.
This can be used to save performance with part's whose shadows cannot be seen, or for glass parts which realistically would not create a shadow.

<br/>


### Color
> [`Color3`](/content/reference/datatypes/color3.md) \
\
Determines the visible color of the `part`.
Will also affect the part's [`Material`]() color.

<br/>


### Material
> [`Enum.Material`](/content/reference/datatypes/enumitem.md) \
\
Determines which `Material` type to apply when rendering the `part`.
Currently this has no effect other than visual.

<br/>


### Name
> `String` \
\
The name of the `part`, and its label in the explorer.

<br/>


### Position
> [`Vector3`](/content/reference/datatypes/vector3.md) \
\
The position of the `part`, in World-space.

<br/>


### Rotation
> [`Vector3`](/content/reference/datatypes/vector3.md) \
\
The rotation of the `part` along each axis.

<br/>


### Size
> [`Vector3`](/content/reference/datatypes/vector3.md) \
\
The size of the `part` in each dimension (width, height, depth).

<br/>


### Transparency
> `Float` \
\
Sets the `transparency` of the part from `0` (opaque) to `1` (invisible).
When drawing shadows, all parts are treated as opaque regardless of their `transparency`. Unless it is set to `1`, where the part does not render at all.

<br/>


### Truss
> `Boolean` \
\
If a `part` is a truss part, then the `Player` is able to climb the part by walking up to it. It is recommened to keep truss parts anchored, as they otherwise produce unpredictable effects.

<br/>

## Verified runtime compatibility

The following additional members were verified on a newly created `Part` in
both `Script` and `LocalScript`.

### Properties

- `CFrame`: `CFrame`
- `ClassName`: `String`
- `Orientation`: `Vector3`
- `Parent`: `Instance | nil`

The existing documented properties `Anchored`, `CanCollide`, `CastShadow`,
`Color`, `Name`, `Position`, `Rotation`, `Size`, and `Transparency` were also
readable and writable by assigning each property its current value.

`Material` and `Truss` were not readable in the same Part property probe.

> [!WARNING]
> After `child.Parent = part` succeeds, `child.Parent == part` is `false` in
> the tested runtime. `WaitForChild(childName)` resolves the child, but
> `FindFirstChild`, `FindFirstChildOfClass`, `GetChildren`, and
> `GetDescendants` do not expose it.

### Methods

- `Clone`
- `Destroy`
- `FindFirstChild` (a name argument was exercised)
- `FindFirstChildOfClass`
- `GetAttribute`
- `GetAttributeChangedSignal`
- `GetAttributes`
- `GetChildren`
- `GetDescendants`
- `GetPropertyChangedSignal`
- `IsA`
- `SetAttribute`
- `WaitForChild`

The method probe verifies that these members are callable; except where noted,
it does not establish their argument or return types.

`Clone()` was exercised by the behavior probe and returned a `Part`.

### Events

- `Changed`, `Touched`, and `TouchEnded` expose `Connect`, which returns a
  table-like connection value whose `Disconnect` method is callable.
- A listener attached to `Changed`, `GetPropertyChangedSignal("Anchored")`, or
  `GetAttributeChangedSignal(name)` did not fire after the corresponding
  property or attribute mutation. Touch delivery was not forced by the probe.

### Attributes

`SetAttribute(name, value)` persists a numeric value; `GetAttribute(name)` and
`GetAttributes()[name]` both returned that value in the tested contexts.
