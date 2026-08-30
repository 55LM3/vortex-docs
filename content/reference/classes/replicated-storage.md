---
title: ReplicatedStorage
description: Contains instances that are loaded by both the server and the client.
---

## Summary
ReplicatedStorage is a container for items that should be visible to both the server and the client. Items placed here will automatically get their properties synced from the server.

## Verified runtime compatibility

`ReplicatedStorage` was available in both `Script` and `LocalScript`.

### Properties

- `ClassName`: `String`
- `Name`: `String`

### Methods

- `FindFirstChild` — callable member.
- `GetChildren` — callable member.
- `WaitForChild` — callable member.

> [!WARNING]
> A temporary Part could be parented to `ReplicatedStorage`, and `WaitForChild`
> found it, but `FindFirstChild` returned `nil` and `GetChildren` omitted it in
> both tested contexts.
