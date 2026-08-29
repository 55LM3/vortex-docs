---
title: Attributes
description: Attributes are basically custom properties that can be given to an Instance. These properties can be Strings, Booleans, and Numbers (Bare Minimum, confirmation is needed for other datatypes.)

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
The SetAttribute Method is used for modifying an attributes value. If the value given is nil, the attribute will be removed.
#### Examples
In the code snippet below, it sets the `"Transparent"` Attribute of the Part to `true`.
```luau
local Part = workspace:WaitForChild("Part")
Part:SetAttribute("Transparency", 1)
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
In the code snippet below it retrieves the Transparency Attribute and then prints it.
```luau
local Part = workspace:WaitForChild("Part")
local Transparency = Part:GetAttribute("Transparency")
print("Transparency)
```


### Creating Attributes
Stub

