---
title: Attributes
description: Attributes are basically custom properties that can be given to an Instance. These properties can be any of the supported Variant data types.

Note: Variant = Any type.
---

### Methods
___________________
### SetAttribute
Sets a pre-existing attributes value to a new value.
```
Instance:SetAttribute(Attribute: String, Value: Variant)
```
#### Parameters

```
Attribute: string
The Name of the attribute being set.
```
```
Value: Variant
The Value to set the specified Attribute to.
```

#### Returns
```
()
```
The SetAttribute Method is used for modifying an attributes value or creating a new attribute value if there is no attribute. If the value given is nil, the attribute will be removed.
#### Examples
In the code snippet below, it sets the `"Id"` Attribute of the Part to `1`.
```luau
local Part = workspace:WaitForChild("Part")
Part:SetAttribute("Id", 1)
```

___________________
### GetAttribute

```
Instance:GetAttribute(Attribute: String): Variant
```
#### Parameters

```
Attribute: string
The Name of the attribute being retrieved.
```
#### Returns
```
Variant
The Value which has been given to the Attribute name. If no value is given to the Attribute name then nil is returned.
```
The GetAttribute Method is used for retrieving the Value set to the Attribute name.
#### Examples
In the code snippet below it retrieves the Id Attribute and then prints it.
```luau
local Part = workspace:WaitForChild("Part")
local Id = Part:GetAttribute("Id")
print(Id)
```

___________________
### GetAttributes
GetAttributes returns a dictionary of the attributes in an Instance.

___________________
### GetAttributeChangedSignal
```
Instance:GetAttributeChangedSignal(Attribute: string)
```

#### Parameters
```
Attribute: String
The name of the specified attribute for which the change signal is being returned. 
```
#### Returns
```
ScriptSignal
An event that fires when the specified attribute changes.
```
### Creating Attributes
Stub

## Vortex Studio 0.3.4 notes

`SetAttribute`, `GetAttribute`, `GetAttributes`, and removal through
`SetAttribute(name, nil)` are confirmed on `Part` instances. `GetAttributes`
returns a table containing the current values.

`GetAttributeChangedSignal` returns a connectable signal, but setting or
removing a Part attribute did not deliver the callback in the tested runtime.
Do not rely on that signal for game logic until delivery is established.

The current player's `Character` Model is an important exception to the
client/server boundary: a confirmed server Script set a temporary Character
attribute to `42`, then `25`; a LocalScript observed both values by polling
`LocalPlayer.Character:GetAttribute`. Server-to-client Character attribute
replication is therefore confirmed. Use polling rather than
`GetAttributeChangedSignal`, whose callback delivery remains unconfirmed.

Client-to-server Character attribute replication is also confirmed for value
changes: a LocalScript set `42`, then `25`, and a server Script observed both
transitions through `Players:GetPlayers()[1].Character:GetAttribute`. Do not
treat these attributes as trusted client input; a client can write values that
the server sees.
