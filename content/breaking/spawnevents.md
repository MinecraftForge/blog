---
title: "Spawn Events Refactor; Breaking Change"
date: 2023-03-23T18:25:19Z
draft: false
categories:
- Breaking Changes
author: forgeteam
summary: "Spawn Events are broken, so we fixed them! Minor breaking changes ahoy."
description: "Spawn Events are broken, so we fixed them! Minor breaking changes ahoy. If you used SpecialSpawn or CheckSpawn, they were most likely not working anyway."
---

# Spawn Events
### The Problem
So, let's talk about spawn events. There's two of them, `SpecialSpawn` and `CheckSpawn`. Both were introduced way back in [2013](https://github.com/MinecraftForge/MinecraftForge/commit/3a9c7b4532240b70dac5f72082cbcedc0dd41335)
and haven't been changed a whole lot since, even though everything around them has. They have their issues, from lack of context to
making completely false claims about their functionality. For example, the javadocs on `SpecialSpawn` state: `If the event is canceled, the mob will not spawn.`
This is not the case, as cancelling the event is _supposed_ to cancel the call to `Mob#finalizeSpawn` (which used to be called `specialSpawn`).
Even more confusingly, in one case, this event _will_ cancel the spawn! It's a tad bizzare. `CheckSpawn` has similar issues.

### The Solution
Well, for the first part, I've simply deleted `SpecialSpawn` and `CheckSpawn`. From the ashes rises a new event named `FinalizeSpawn`, which
is the end-all-be-all to a spawn event. This event fires on all invocations of `Mob#finalizeSpawn` (targets are automatically injected by coremod), and gives
total control over the spawn. You can:
* React to any mob spawn, without missing edge cases due to missed patch targets.
* Cancel the call to `Mob#finalizeSpawn`
* Cancel the entire spawn (without using `EntityJoinLevelEvent`)
* Adjust the spawn rules by changing the local difficulty instance or the spawn group data.
* Add custom armor, attributes, or other bonuses to a spawned mob, without being overridden by vanilla.

Additionally, mobs will now record their spawn type for their lifetime, meaning you can make functionality that depends on mobs being 
spawned from a specific source. For me, this change helps me add drops only to naturally-spawned mobs, without relying on fragile 
tracking methods.

### Porting
Porting from the old events to the new one should be simple. If you were using `SpecialSpawn`, you can just rename to `FinalizeSpawn`.
If you were using `CheckSpawn`, you can utilize `FinalizeSpawn#setSpawnCancelled` to block spawns.
There's a bit of lost functionality though - if you were using `CheckSpawn` to forcibly allow the spawn of natural entities, meaning
those that spawn ambiently on chunk ticks (not including ones during chunk generation), there's no replacement.
Nobody voiced a concern that this functionality was necessary, so it was dropped. It was the only instance where `CheckSpawn` used
its result, but this was misleading, as `CheckSpawn` stipulated that it would work in all cases of it firing.

### Technical Things
As mentioned earlier, `FinalizeSpawn` is injected with a coremod, instead of with the traditional patch method. This means we'll never
need to manually hunt for new targets (which is a major reason so many spawns didn't fire `SpecialSpawn`). It also means this method
can now be used for other events with a high patch surface, as the underlying code is very adaptable. The only downside to this approach
is that these changes aren't source-visible, which means there's a higher burden to document exactly where the calls will occur.
