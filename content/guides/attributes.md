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
This event fires whenever a Attribute is changed.

### Creating Attributes
Stub

