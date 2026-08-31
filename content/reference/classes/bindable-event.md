---
title: BindableEvent
description: Bindable events are objects that allow for communication between two scripts on the same side of the client-server boundary. Scripts firing BindableEvents do not yield.
---

Notes: Tuples are list of values.

## Summary
#### Methods
```
Fire (Arguments: Tuple): ()
```
#### Events
```
Event (Arguments: Tuple): ScriptSignal
```
The BindableEvent object is an object which allows custom one way asynchronous communication between scripts on the same side of the client-server boundary. When you fire a Bindable event in a script through the BindableEvent:Fire() method, the firing script does not yield and the target function receives the passed arguments with certain limitations. BindableEvents create threads of each connected function, so even if one firing errors, others continue. 

As stated, BindableEvents do not allow for communication between the server and clients. If you are looking for this functionality, use a RemoteEvent.

## API reference
### Methods
### Fire
Fires the Bindable event which in turn fires the Event event.
```
BindableEvent:Fire(arguments:Tuple):()
```
#### Parameters
```
Arguments: Tuple
Values to pass to Event events connected to the same BindableEvent.
```
#### Returns
```
()
```
### Events
### Event
Fires when any script calls the Fire() method on the specified BindableEvent.
```
BindableEvent.Event(arguments:Tuple):RBXScriptSignal
Values to pass to Event events connected to the same BindableEvent.
```
#### Parameters
```
arguments: Tuple
The parameters sent through Fire().
```
#### Returns
```
()
```

## Examples and guides
### Creating BindableEvents
To create a BindableEvent you must click on the side of ReplicatedStorage, then click the plus icon, and then select BindableEvent. It is recommended you store your BindableEvents in Folders. For example, create a folder called "Networking" and then inside folder create another Folder called BindableEvents, and then inside that folder you can have other Folders to hold BindableEvents for specific uses.

### Using BindableEvents
In the code snippet below, i will reference the Bindable event, and then fire it inside a ServerScript in ServerScriptService to tell another ServerScript the Status of the Door.
#### Server Script 1
```luau
local ReplicatedStorage = game:GetService("ReplicatedStorage")
local DoorEvent = ReplicatedStorage:WaitForChild("DoorEvent")

task.wait(1)

DoorEvent:Fire("Open")
print("Fired.")
```
Serverscript 1 fires the BindableEvent and sends over the status of the Door.
#### Server Script 2
```luau
local ReplicatedStorage = game:GetService("ReplicatedStorage")
local DoorEvent = ReplicatedStorage:WaitForChild("DoorEvent")

DoorEvent.Event:Connect(function(Status)
	print("Door Status: ", Status)
end)
```
Serverscript 2 recieves the BindableEvent and then prints the status of the Door
