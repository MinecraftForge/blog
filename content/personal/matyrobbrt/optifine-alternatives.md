---
title: "OptiFine Alternatives"
date: 2023-04-25T21:15:02+03:00
draft: false
categories:
- Personal Blog
author: matyrobbrt
summary: "Let's talk about OptiFine and alternatives for it!"
description: "OptiFine is known for breaking modded environments. In this post, we'll talk about some alternatives to it."
---
### Note: these mods are not officially supported nor endorsed by Forge!

OptiFine has started as a simple optimization mod for Minecraft. However, over the years, it has had more features implemented, its stability has been gradually decreasing and the amount of issues it has caused modders have... increased substantially.

## How does OptiFine work. Why is it problematic?
OptiFine uses [Xdelta](http://xdelta.org/), an
> open-source binary diff, differential compression tool

in order to modify the binary classes of the game. This means that, it ends up replacing entire methods or even classes. This becomes problematic when used with Forge, as it can easily revert Forge modifications, and, as such, cause issues.

Additionally, OptiFine heavily rewrites rendering code, causing graphical glitches when used in conjunction with mods.

### Closed-source
*Tip*: sciwhiz12 [has published](../../sciwhiz12/what-are-mappings/) a blog post about Mappings, which talks about some of the software mentioned below in-depth.

Publishing OptiFine sources verbatim would result in legal issues as it contains decompiled Minecraft artifacts. Technically, it would be possible to extract the actual changes as patches, which can then be published to GitHub as source code, similarly to how Forge does it, but maintaining that is too much effort for a single person.

However, there are other issues as well. OptiFine is built on a custom version of Mod Coder Pack. According to the MCP license and Terms of Usage, modified versions of MCP scripts are not allowed to be distributed.
Back in the day, the usage of a custom MCP version allowed OptiFine to start development on new versions of the game much, much earlier. But on modern versions, with Mojang releasing their official mappings,
MCP has been made obsolete. A switch to the official mappings would however imply remapping the entirety of OptiFine's codebase, which takes effort.

For the above reasons, OptiFine is still, to this day, closed source. When taking into account the fact that the only source of OptiFine changes are the Xdelta binary patches, mod developers will have a hard time integrating with OptiFine as they are not able to properly debug issues they encounter with it. Therefore, most mods are not and will not be compatible with OptiFine.

## Alternatives
While OptiFine is mainly advertised as a performance mod, it is worth noting that it also has some other client-side features, such as dynamic lights or connected textures.

Below you will find a list of alternative mods for different OptiFine features, in no order:

- Connected textures: [CTM](https://www.curseforge.com/minecraft/mc-mods/ctm)
- Leaf culling: [Cull Leaves](https://www.curseforge.com/minecraft/mc-mods/cull-leaves)
- Entity culling: [Entity Culling](https://www.curseforge.com/minecraft/mc-mods/entityculling)
- Dynamic lights: [Dynamic Lights](https://www.curseforge.com/minecraft/mc-mods/dynamic-lights)
- Fog control: [NoFog](https://www.curseforge.com/minecraft/mc-mods/nofog)
- Entity textures: [Entity Textures Features](https://www.curseforge.com/minecraft/mc-mods/entity-texture-features-fabric)
- Extended texture animations: [MoreMcmeta](https://www.curseforge.com/minecraft/mc-mods/moremcmeta)
- Transparent entity textures: [Transparent](https://www.curseforge.com/minecraft/mc-mods/transparent)
- Shaders: [Oculus](https://www.curseforge.com/minecraft/mc-mods/oculus)

## Conclusion
There are mods that implement almost all OptiFine features. There is no need to keep on using OptiFine and constantly risking to be exposed to weird issues when playing your favourite modpacks!
