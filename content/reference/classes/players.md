---
title: Players
description: A container that holds all players currently connected as Player objects.
---

## Verified runtime compatibility

`Players` was available in both `Script` and `LocalScript`.

### Properties

- `ClassName`: `String`
- `Name`: `String`
- `LocalPlayer`: available in `LocalScript`; absent in the tested `Script`
  context.

### Methods

- `GetPlayers` — returns a table. In the one-player test, it contained one
  player in `LocalScript` and no players in `Script`; counts are runtime-state
  dependent.
