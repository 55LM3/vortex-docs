### GetDescendants()

> `Array`
>
> Returns an array containing all descendants of the instance. This includes children, grandchildren, and any other objects nested inside the instance.
>
> ```lua
> local descendants = workspace:GetDescendants()
> ```
>
> Unlike `GetChildren()`, `GetDescendants()` searches through the entire hierarchy below the instance.
