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

These observations are from Vortex Studio 0.3.3, the current public build, and
may differ in later releases.

A detached `Model` exposes the generic instance members and no readable
`Position`, `PrimaryPart`, or `WorldPivot` property. Setting a temporary
Part's `Parent` to a detached Model did not establish an observable hierarchy:
parent equality was `false`, `FindFirstChild` returned `nil`, `GetChildren()`
returned an empty table, and `WaitForChild` did not return the temporary Part.
