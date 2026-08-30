### lookAt(Position: `Vector3`, LookAt: `Vector3`)

[svg](https://github.com/Nullvss/vortex-docs/blob/main/content/reference/datatypes/cframe.md#lookatposition-vector3-lookat-vector3)

> `CFrame`
>
> Returns a new `CFrame` positioned at `Position` and oriented toward `LookAt`.
>
> ```lua
> local position = Vector3.new(0, 5, 0)
> local target = Vector3.new(0, 5, -10)
>
> local cf = CFrame.lookAt(position, target)
> ```
>
> The example above creates a `CFrame` at the given position facing toward the target position.
