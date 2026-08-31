---
title: Scripts and VMs
description: Learn more about scripts and how Luau source code operates at runtime.
---

# Scripts

A script is a container that holds Luau source code. Scripts are used to define gameplay logic and interact with the engine.

Here's an example of this:
```lua 
local part = Instance.new("Part)
part.Parent = game.Workspace
```
> [!NOTE]
> All though this script just defines a variable and changes a property, there's much more you can do that would take ages to document.

The source code in a script does **not directly execute Luau instructions. It's contents are passed onto the Luau VM for execution.**
All types of current scripts:
* LocalScripts
* Scripts

# Luau Virtual Machine 

The Luau VM is responsible at runtime for executing Luau code. 
When a script runs, the engine passes it's source code (the scripts) to the Luau runtime. The Luau VM then executes the code and **manages the state while the code is running.**

Here's an example of how the flow works: 


Script → Luau Source Code → Luau Compiler → Bytecode → Engine APIs (which is **_Bevy_**) → Game


