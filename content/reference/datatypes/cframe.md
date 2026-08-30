---
title: CFrame
description: A data type that represents both a 3D position and orientation.
---------------------------------------

<link rel="stylesheet" href="/styles/test.css">

<!-- 
CFrame
Revision 1

Written by n1run on August 29th, 2026
-->

> [!NOTE] 
> CFrames do not exist in Vortex right now, so all of this information is taken from Roblox's CFrame.

## Summary

<details>
<summary><b>Properties</b></summary>
Properties of a `CFrame`.
<br><br>

* [Position](#position): `Vector3`
* [Rotation](#rotation): `CFrame`
* [X](#x): `Number`
* [Y](#y): `Number`
* [Z](#z): `Number`
* [LookVector](#lookvector): `Vector3`
* [RightVector](#rightvector): `Vector3`
* [UpVector](#upvector): `Vector3`
* [XVector](#xvector): `Vector3`
* [YVector](#yvector): `Vector3`
* [ZVector](#zvector): `Vector3`

</details>

<details>
<summary><b>Constructors</b></summary>
Constructors of a `CFrame`.
<br><br>

* [new()](#new): `CFrame`
* [new(Position: `Vector3`)](#newposition-vector3): `CFrame`
* [new(X: `Number`, Y: `Number`, Z: `Number`)](#newx-number-y-number-z-number): `CFrame`
* [Angles(RotationX: `Number`, RotationY: `Number`, RotationZ: `Number`)](#anglesrotationx-number-rotationy-number-rotationz-number): `CFrame`
* [lookAt(Position: `Vector3`, Target: `Vector3`)](#lookatposition-vector3-target-vector3): `CFrame`

</details>

## Properties

### Position

> `Vector3`
>
> The 3D position component of the CFrame.

<br/>

### Rotation

> `CFrame`
>
> The 3D rotation component of the CFrame, with the position components reset to zero.

<br/>

### X

> `Number` 
>
> The X-axis coordinate of the CFrame's position component.

<br/>

### Y

> `Number` 
>
> The Y-axis coordinate of the CFrame's position component.

<br/>

### Z

> `Number` 
>
> The Z-axis coordinate of the CFrame's position component.

<br/>

### LookVector

> `Vector3` 
>
> A normalized vector pointing in the forward direction of the CFrame.

<br/>

### RightVector

> `Vector3` 
>
> A normalized vector pointing in the right direction of the CFrame.

<br/>

### UpVector

> `Vector3` 
>
> A normalized vector pointing out of the top side of the CFrame.

<br/>

### XVector

> `Vector3`
>
> The X component of the CFrame's rotation matrix. Equivalent to RightVector.

<br/>

### YVector

> `Vector3`
>
> The Y component of the CFrame's rotation matrix. Equivalent to UpVector.

<br/>

### ZVector

> `Vector3`
>
> The Z component of the CFrame's rotation matrix. Equivalent to the negated LookVector (-LookVector).

<br/>

## Constructors

### new()

> `CFrame`
>
> Returns a blank `CFrame` located at the world origin with no rotation.

<br/>

### new(Position: `Vector3`)

> `CFrame`
>
> Returns a new `CFrame` from a given `Vector3` position with no rotation.

<br/>

### new(X: `Number`, Y: `Number`, Z: `Number`)

> `CFrame`
>
> Returns a new `CFrame` from the given spatial coordinates with no rotation.

<br/>

### Angles(RotationX: `Number`, RotationY: `Number`, RotationZ: `Number`)

> `CFrame`
>
> Returns a new `CFrame` rotated around the X, Y and Z axes by the given angles specified in radians.

<br/>

### lookAt(Position: `Vector3`, Target: `Vector3`)

> `CFrame`
>
> Returns a new `CFrame` located at the `Position` coordinates and rotated to point directly toward the `Target` coordinates.

<br/>
