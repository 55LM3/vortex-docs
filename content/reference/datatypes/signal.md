---
title: Signal
description: A connectable runtime event.
---

## Verified runtime compatibility

`Signal.Connect` is a callable member. The probes verified this by reading
`Connect` from `Instance.Changed`, `Part.Touched`, `Part.TouchEnded`, and
`UserInputService.InputBegan`.

Each tested connection returned a table-like value whose `Disconnect` method
was callable. Mutating a Part did not deliver its `Changed`, property-changed,
or attribute-changed callbacks in the test. A live keyboard test did deliver
`UserInputService.InputBegan` callbacks; see that service's event reference
for its observed payload.
