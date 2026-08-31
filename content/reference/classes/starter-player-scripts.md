---
title: StarterPlayerScripts
description: Container inside the "StarterPlayer" Service that stores Client-side scripts
---

# What is StarterPlayerScripts?

**StarterPlayerScripts** is a container inside the "StarterPlayer" service that stores Client-side scripts on a players entry into the experience.

> [!CAUTION]
> Do not confuse StarterPlayerScripts with StarterCharacterScripts. Although they are similar, they have different functions (and by "functions", I mean purposes.)

It's usually used for scripts that control player behavior and systems that run on the player's device.

# What is StarterPlayerScripts used for? 

It's commonly used for:
* Client-side game systems
* Player input handling
* Camera systems
* Client-side effects and animations
* User interface logic
* Keyboard, mouse, and controller input
* Local player movement systems
* Client-side visual effects

# Other things and expanding more into how it works

Scripts that are placed in StarterPlayerScripts are automatically copied into the player's PlayerScripts container on join. 
StarterPlayerScripts was designed with the intent that it's supposed to be mainly used for LocalScripts.
> [!NOTE]
> Do not try creating a server script in StarterPlayerScripts. It will not run at all. ModuleScripts can be used in StarterPlayerScripts for modules that handle player-logic (client-only). Otherwise, consider using ReplicatedStorage.

Lastly, do NOT (NOT!!) trust StarterPlayerScripts as scripts here supposed to be used for client-side logic.
> [!CAUTION]
> Using S.P.S for server-logic (such as server validation) is the equivalent of inviting a robber into your house. Don't trust it.
