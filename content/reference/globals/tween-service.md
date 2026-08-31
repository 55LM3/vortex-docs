---
title: TweenService
description: Explains TweenService and provides code examples
---
TweenService is a way that you can change different properties of parts over a certain amount of time with different easing styles. You can get tween service by using the game:GetService function
```
local TweenService = game:GetService("TweenService")
```
Now, lets make a simple TweenService function that moves a part!

```
local TweenService = game:GetService("TweenService") -- Get the tween service

local part = workspace:FindFirstChild("TweenPart") 
```
Gets the tween service and gets a part for the tween. You can use any part for this or even create one with [Instance.new](https://create.playvortex.io/reference/globals/instance-new/), it just has to be a valid part.
```
local tweenInfo = {
    2,
    Enum.EasingStyle.Linear,
    Enum.EasingDirection.Out
}
```
Here is the tween info. The first value is how long the tween will last, the second is the easing
style, and the third is the easing direction. You can find all of the easing style and easing directions on the [Enum](https://create.playvortex.io/reference/globals/enum/) page.

```
local tweenGoal = {
    Position = Vector3.new(0, 5, 0),
    Color = Color3.fromRGB(137, 111, 255)
}
```
Here is the tween goal. This is the result of the tween. You can change the properties of a part, such as Position, Color, and Transparency. Here it moves the part and changes the color to the classic Vortex purple.

```
local tween = TweenService:Create(part, tweenInfo, tweenGoal)

tween:Play()
```
This creates the tween itself using the part, tweenInfo, and tweenGoal we just defined.

Click Play, and congratulations, you have just made your first tween!
