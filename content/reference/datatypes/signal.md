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

## Testing Notes

These observations are from Vortex Studio 0.3.3, the current public build, and
may differ in later releases.

Connections are represented as tables. Mutating a `Part` does not deliver its
`Changed`, property-changed, or attribute-changed callbacks. Keyboard input
does deliver `UserInputService.InputBegan` callbacks.
