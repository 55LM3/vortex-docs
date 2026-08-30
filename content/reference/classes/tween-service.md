---
title: TweenService
description: Creates Tween objects for instance-property animation.
---

`TweenService` is available through `game:GetService("TweenService")`.

## Summary

<details>
<summary><b>Methods</b></summary>
Methods of `TweenService`.
<br><br>

* [Create](#create): [`Tween`](/content/reference/datatypes/tween.md)

</details>

## Methods

### Create

> [`Tween`](/content/reference/datatypes/tween.md)
>
> `TweenService:Create(instance: Instance, tweenInfo: TweenInfo, propertyTable: table)`
>
> Creates a Tween targeting the supplied properties of `instance`.

#### Parameters

- `instance`: `Instance` — the object whose properties the Tween targets.
- `tweenInfo`: `TweenInfo` — the animation configuration.
- `propertyTable`: `table` — property names mapped to their target values.

## Testing Notes

These observations are from Vortex Studio 0.3.3, the current public build, and
may differ in later releases.

`Create` returned a Tween in both `Script` and `LocalScript` when given an
unparented `Part`, `TweenInfo.new(0.1)`, and `{ Transparency = 0.5 }`.
