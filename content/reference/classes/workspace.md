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
<ul>
<details>
<summary><b>Appearance</b></summary>
</details>

<details>
<summary><b>Transform</b></summary>

</details>

</ul>
</details>


## Verified runtime compatibility

The following surface was verified in both `Script` and `LocalScript`.

### Properties

- `ClassName`: `String`
- `Name`: `String`

### Methods

- `FindFirstChild` — callable member.
- `GetChildren` — callable member.
- `WaitForChild` — callable member.

Other documented `Workspace` methods, including `Raycast`, were not exposed by
the tested member probe.

> [!WARNING]
> A temporary Part could be parented to `Workspace`, and `WaitForChild` found
> it, but `FindFirstChild` returned `nil` and `GetChildren` omitted it in both
> tested contexts.
