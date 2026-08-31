---
title: BindableEvent
description: Bindable events are objects that allow for communication between two scripts on the same side of the client-server boundary. Scripts firing BindableEvents do not yield.
---


> A `Tuple` is an ordered sequence of values that can be passed between scripts.

## Summary

#### Methods

```text
Fire(arguments: Tuple): ()
```

#### Events

```text
Event: ScriptSignal
```

A `BindableEvent` allows custom, one-way, asynchronous communication between scripts on the same side of the client-server boundary.

When a script calls `BindableEvent:Fire()`, the calling script does not yield while the connected event handlers are executed. The arguments passed to `Fire()` are provided to each connected handler.

Each connected handler runs independently, meaning an error in one handler does not prevent other connected handlers from running.

`BindableEvent`s cannot be used to communicate between the server and clients. For communication across the client-server boundary, use a `RemoteEvent`.

## API Reference

### Methods

### Fire

Fires the `Event` signal and passes the supplied arguments to all connected handlers.

```text
BindableEvent:Fire(arguments: Tuple): ()
```

#### Parameters

```text
arguments: Tuple
```

The values to pass to handlers connected to the `Event` signal.

#### Returns

```text
()
```

Nothing.

### Events

### Event

Fires whenever `Fire()` is called on the `BindableEvent`.

```text
BindableEvent.Event: ScriptSignal
```

The connected handler receives the values passed through `Fire()`.

#### Parameters

```text
arguments: Tuple
```

The values supplied by the call to `Fire()`.

#### Returns

```text
()
```

The event itself does not return a value. The connected handler may return values, but those values are not returned through the `BindableEvent`.

## Examples and Guides

### Creating BindableEvents

To create a `BindableEvent`, add one through the object creation menu in Vortex Studio. It is recommended to organize `BindableEvent`s inside folders when working with multiple events.

For example, you could create a folder named `Networking` and place your `BindableEvent`s inside it.

### Using BindableEvents

The following example shows one server-side script firing a `BindableEvent` and another server-side script receiving it.

#### Server Script 1

```luau
local ReplicatedStorage = game:GetService("ReplicatedStorage")
local DoorEvent = ReplicatedStorage:WaitForChild("DoorEvent")

task.wait(1)

DoorEvent:Fire("Open")
print("Fired.")
```

This script fires the `DoorEvent` and passes `"Open"` as the door status.

#### Server Script 2

```luau
local ReplicatedStorage = game:GetService("ReplicatedStorage")
local DoorEvent = ReplicatedStorage:WaitForChild("DoorEvent")

DoorEvent.Event:Connect(function(status)
	print("Door Status:", status)
end)
```

This script connects to the `DoorEvent` and receives the status passed by the first script.
