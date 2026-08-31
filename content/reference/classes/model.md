---
title: Model
description: A collection of explorer items, grouped into one object
---

<!-- 
Model
Revision 1

Written by KingTasaz on August 28th, 2026
-->

## Summary
Models are a very simple way to group [`parts`](/content/reference/classes/part.md) together.
Creating a model requires at least `2` parts selected, but otherwise the second part can be deleted. Parts in a model are not truly connected, but only grouped in the explorer. Models currently have no purpose other than organization.

A model with no children is still shown in the explorer, but does not exist in the world and has no transform controls.

The basic transform tools (Move, Rotate) work more or less as expected when used on a model, except for scaling which currently is not properly supported.

<details>
<summary><b>Properties</b></summary>
Properties of a Model, in the order they appear on Vortex Studio.
<br><br>
<ul>

<details>
<summary><b>Properties</b></summary>

- [Name](#name): `String`

</details>

</ul>
</details>

## Properties


### Name
> `String` \
\
The name of the `model`, and its label in the explorer.

<br/>


## Images
<img src="../../../images/modelCenterExample1.png" alt="Model w/ Move Tool" width="400"/>

## Testing Notes

In Vortex Studio 0.3.4, a detached `Model` exposes the generic instance
surface, including hierarchy and attribute methods, but has no readable
`Position`, `PrimaryPart`, or `WorldPivot` property. This is identical in
both Script and LocalScript.

Setting a temporary Part's `Parent` to a detached Model does not establish an
observable hierarchy: parent equality is `false`, `FindFirstChild` returns
`nil`, `GetChildren()` returns an empty table, and `WaitForChild` does not
return the temporary Part.

`GetPivot`, `PivotTo`, `GetPrimaryPartCFrame`, and `SetPrimaryPartCFrame` are
also unavailable (`nil`) in both contexts. Assigning `Model.PrimaryPart` is
rejected as a non-settable property.

In 0.3.4, the live Character Model is a special case: it supports attributes,
and Character attribute values replicate in both directions between a server
Script and the owning LocalScript. See the [Attributes guide](/content/guides/attributes.md).
