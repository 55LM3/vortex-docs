---
title: Debris
description: A service that allows removal of instances without yielding.
---

<!--
Debris
Revision 1

Written by TheJustDare on August 30th, 2026
-->

## Summary

> [!NOTE]
> `Debris` is available through `game:GetService("Debris")` in both `Script`
> and `LocalScript`. Repeated lookups compared equal in the tested runtime.

The broad signal probe found none of its ten checked generic Instance signals
on `Debris`.

<details>
<summary><b>Syntax</b></summary>

`Debris:AddItem(instance: Instance, lifetime: number): ()`

</details>

## Overview

`Debris` is a service that allows removal of instances without yielding for objects that may lose utility after a set period of time.

```lua
local Debris = game:GetService("Debris")

local part = Instance.new("Part")
part.Parent = workspace

Debris:AddItem(part, 5)
```

## Lifetime

The `AddItem()` method won't execute unless a lifetime parameter is given.

The lifetime can be set to any number from positive to negative range.
