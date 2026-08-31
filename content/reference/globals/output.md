---
title: Output
description: The Output window in Vortex is used to display messages, warnings, errors, and other information.
---

# What appears in output?

A plethora of things. Firstly, you'll see errors from your scripts (as shown below):
```
[Script] line 1: attempt to call a nil value
stack traceback:
	[string "script:4294966667"]:1: in ?
```
> [!NOTE]
> To reproduce this error, create a server script and try using the "warn" function (doesn't exist at the time of writing) `warn("This function does not exist.")`

Secondly, you can see things you print (as shown below):
```
[Script] Hello, World!
```
> [!NOTE]
> To reproduce this output, use the `print()` function.


# Summary
The Output is used to view print messages and warnings.
