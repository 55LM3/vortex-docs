---
title: Signal
description: An event object that invokes connected callbacks.
---

> `Signal`
>
> An event-based object used to communicate when something happens. A `Signal` can be fired to notify connected functions that an event has occurred.
>
> Signals are commonly used for handling events and communicating between different parts of a script.

## Summary

<details>
<summary><b>Methods</b></summary>
Methods of a `Signal`.
<br><br>

* [Connect](#connect): [`Connection`](/content/reference/datatypes/connection.md)
* [Fire](#fire)
* [Once](#once): [`Connection`](/content/reference/datatypes/connection.md)
* [Wait](#wait): `...any`

</details>

<details>
<summary><b>Constructors</b></summary>
Constructors of a `Signal`.
<br><br>

* [new](#new): `Signal`

</details>

## Methods

### Connect()

> [`Connection`](/content/reference/datatypes/connection.md)
>
> `signal:Connect(callback: Function)`
>
> Connects `callback` to the signal and returns a connection.

#### Parameters

- `callback`: `Function` — called when the signal fires.

<br/>

### Fire()

> `signal:Fire(...arguments: any)`
>
> Synchronously invokes connected callbacks with the supplied arguments.

#### Parameters

- `...arguments`: `any` — values passed to each connected callback.

<br/>

### Once()

> [`Connection`](/content/reference/datatypes/connection.md)
>
> `signal:Once(callback: Function)`
>
> Connects `callback` for the next fire only and returns a connection.

#### Parameters

- `callback`: `Function` — called the first time the signal fires after connection.

<br/>

### Wait()

> `...any`
>
> `signal:Wait()`
>
> Yields the current thread until the signal fires, then returns the arguments
> supplied to `Fire`.

<br/>

## Constructors

### new()

> `Signal`
>
> `Signal.new(name: String)`
>
> Creates a standalone signal that can be connected to and fired.

#### Parameters

- `name`: `String` — a caller-supplied signal name.

## Testing Notes

These observations are from Vortex Studio 0.3.3, the current public build, and
may differ in later releases.

Connections are represented as tables. Mutating a `Part` does not deliver its
`Changed`, property-changed, or attribute-changed callbacks. Keyboard input
does deliver `UserInputService.InputBegan` callbacks.

The lowercase `connect` and `fire` aliases are also exposed, but the reference
uses the canonical `Connect` and `Fire` names.
