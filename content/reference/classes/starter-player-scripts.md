---
title: StarterPlayerScripts
description: Script container service.
---

## Verified runtime compatibility

`StarterPlayerScripts` was available in both `Script` and `LocalScript`.

### Properties

- `ClassName`: `String`
- `Name`: `String`

### Methods

- `FindFirstChild` — callable member.
- `GetChildren` — callable member.
- `WaitForChild` — callable member.

> [!WARNING]
> A temporary Part could be parented to `StarterPlayerScripts`, and
> `WaitForChild` found it, but `FindFirstChild` returned `nil` and
> `GetChildren` omitted it in both tested contexts.
