---

title: Color3
description: A color value comprised of red, green, and blue components.
---

<!-- 
Color3
Revision 1

Written by Kindtracker on August 28th, 2026
-->

> [!NOTE]
> There will be more things (methods, constructors, properties, etc.) in the future. This is based on leaks.

## Summary

<details>
<summary><b>Properties</b></summary>
Properties of a `Color3`.
<br><br>

* [R](#r): `Number`
* [G](#g): `Number`
* [B](#b): `Number`

</details>

<details>
<summary><b>Constructors</b></summary>
Constructors of a `Color3`.
<br><br>

* [new(R: `Number`, G: `Number`, B: `Number`)](#newr-number-g-number-b-number): `Color3`
* [fromRGB(R: `Number`, G: `Number`, B: `Number`)](#fromrgbr-number-g-number-b-number): `Color3`

</details>

## Properties

### R

> `Number`
>
> The red value of the color.

<br/>

### G

> `Number`
>
> The green value of the color.

<br/>

### B

> `Number`
>
> The blue value of the color.

<br/>

## Constructors

### new(R: `Number`, G: `Number`, B: `Number`)

> `Color3`
>
> Returns a new `Color3` from the given values. Values range from `0` to `1`.

<br/>

### fromRGB(R: `Number`, G: `Number`, B: `Number`)

> `Color3`
>
> Returns a new `Color3` from the given values. Values range from `0` to `255`.

<br/>

## Verified runtime compatibility

`Color3.new` and `Color3.fromRGB` were present in both `Script` and
`LocalScript`. `Color3.fromRGB(64, 128, 255)` returned components
`(64 / 255, 128 / 255, 1)`.

The constructor probe found 2 of 4 checked constructors: `new` and `fromRGB`.

`Color3.Lerp(other, alpha)` performs component-wise linear interpolation. For
example, interpolating `(0, 0, 0)` toward `(1, 0.5, 0.25)` with `0.25` returned
`(0.25, 0.125, 0.0625)`.

Adding two `Color3` values fails because Vortex represents them as tables
without an addition metamethod.

> [!NOTE]
> Runtime probes in both `Script` and `LocalScript` verified `new` and
> `fromRGB`. `fromHSV` and `fromHex` were not available in the tested Vortex
> runtime.
