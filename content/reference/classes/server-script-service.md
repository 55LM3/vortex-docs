---
title: ServerScriptService
description: Server script container service.
---

## Verified runtime compatibility

`ServerScriptService` was available in both `Script` and `LocalScript`.

### Properties

- `ClassName`: `String`
- `Name`: `String`

### Methods

- `FindFirstChild` — callable member.
- `GetChildren` — callable member.
- `WaitForChild` — callable member.

> [!WARNING]
> A temporary Part could be parented to `ServerScriptService`, and
> `WaitForChild` found it, but `FindFirstChild` returned `nil` and
> `GetChildren` omitted it in both tested contexts.
