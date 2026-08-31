---
title: StarterPlayerScripts
description: The service surface for editor-authored LocalScripts.
---

## Runtime support

`game:GetService("StarterPlayerScripts")` is available in both Script and
LocalScript contexts in Vortex Studio 0.3.4. It exposes `FindFirstChild`,
`GetChildren`, and `WaitForChild`.

Runtime-created LocalScripts do not become observable children when assigned
to this service. Use an editor-authored LocalScript for client execution;
runtime construction and parenting cannot install new client code.
