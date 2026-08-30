---
title: task
description: Runtime task scheduling helpers.
---

## Verified runtime compatibility

The following `task` library functions were present in both `Script` and
`LocalScript`:

- `task.defer`
- `task.delay`
- `task.spawn`
- `task.wait`

The initial capability probe verifies function presence; the dedicated behavior
probe records the scheduling details below.

`task.cancel`, `task.desynchronize`, and `task.synchronize` were not available
in the same runtime pass.

## Observed scheduling behavior

In both tested contexts, a `task.spawn` callback completed during the scheduling
call itself. A `task.defer` callback and a `task.delay(0, callback)` callback
were both still pending after one `task.wait()` and completed during the second
wait cycle. `task.wait()` returned a number.
