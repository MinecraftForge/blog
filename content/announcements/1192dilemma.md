---
title: "The 1.19.2 Dilemma - Conclusion"
date: 2023-01-01T01:31:36Z
draft: false
categories:
- Announcements
author: curle
summary: "1.19.2 caused a bit of a dilemma for us; do we treat 1.19.3 as a major version and move our LTS from 1.18.2, or do we treat it as a normal breaking change? We asked the community, and the response was.."
description: "1.19.2 caused a bit of a dilemma for us; do we treat 1.19.3 as a major version and move our LTS from 1.18.2, or do we treat it as a normal breaking change? We asked the community, and the response was.."
---

.. not conclusive.

Our vote was, some may say, perfectly balanced: 127 votes for keeping LTS at 1.18.2, and 127 votes for moving LTS to 1.19.2.

## So what does this mean?

Well, there's no clear community consensus. There's no way for us to know what the *majority* of the community want; either because they couldn't be bothered to make an account on our forum, or because there simply wasn't a majority.

If we assume that the 254 votes we had are a representative sample of the overall community (which is a huge if!), then there's only one clear option available to us:

1.18.2 will remain as our LTS version.  
1.19.2 will remain as a valid target for PRs.

## Wait, what?

When we opened this vote, we made [a branch for 1.19.2 on our GitHub repository](https://github.com/MinecraftForge/MinecraftForge/tree/1.19.2). This was made in preparation for the vote being swayed in favor of 1.19.2.

Going forward, we will allow PRs to target this branch, and will publish it separately from 1.19.3.

However, it won't inherit any of our normal LTS policies; as it is not an LTS version, we won't require that people first submit features to 1.19.3, and we won't ask people to backport to 1.19.2.

It comes under the umbrella of "if you want it updated, do it yourself", but we will still help you along with bug fixes and testing and etc if necessary.

1.18.2 will remain as our proper LTS version, and will be the focus of the LTS development and triage teams.  
We just choose to allow PRs to 1.19.2 also.

## Moving forward

It's likely that this is the last time we'll have to make this decision.

Mojang seem to be moving towards a "feature flag update" system, where they add "hidden" content (think pouches) to the game in minor updates, and make it accessible to players in a major update where the only change is to flip the switch on the feature flags that hide them from gameplay.

If that's the case, then we would only need to "fully" support the last major version as LTS, and move our latest along with each minor update.

That release cycle makes sense, in our opinion, for Mojang to do, and relieves a lot of the stress of porting for us.

This is speculation.

However, it seems likely.

## Last minute notes

Along with this decision, we made a new RB for [1.19.3]({{<ref "/releases/1193rb1">}}) and [1.18.2]({{<ref "/releases/1182rb2">}}). This should stabilise those versions a little more, to make our future maintenance a lot easier.

A member of our team has also written [a short porting primer](https://gist.github.com/ChampionAsh5357/c21724bafbc630da2ed8899fe0c1d226) that should help developers update their code to 1.19.3, should they choose to stick with the most recent version of the game.
