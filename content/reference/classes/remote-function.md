---
title: RemoteFunction
description: A request/response remote endpoint between client and server contexts.
---

## Summary

`RemoteFunction` is the request/response counterpart to
[`RemoteEvent`](/content/reference/classes/remote-event.md). Its client
`InvokeServer` member is exposed, and assigning `OnServerInvoke` succeeds in a
Script for an editor-authored remote in `ReplicatedStorage`.

## Methods

- `InvokeServer(...arguments: any): ...any` — exposed on the client.
- `InvokeClient(...arguments: any): ...any` — documented upstream but its
  Vortex delivery behavior has not been established.

## Callbacks

- `OnServerInvoke` — assign a function to handle `InvokeServer` calls.
- `OnClientInvoke` — documented upstream; its Vortex delivery behavior has not
  been established.

## Testing Notes

These observations are from Vortex Studio 0.3.3 and may differ in later
releases.

`InvokeServer(LocalPlayer)` is rejected before server delivery with “Instances
cannot be sent through a RemoteEvent yet”. A successful primitive-value
request/response round trip has not yet been established, so do not rely on it
for gameplay state.
