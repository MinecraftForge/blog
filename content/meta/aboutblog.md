---
title: "About the Blog"
date: 2022-06-19T118:42:12Z
draft: false
categories:
- Blog Meta
author: curle
summary: "About this Blog"
description: "Forge now has an official Blog! Why, what we're going to do with it, and how is it going to help us?"
menu: main
---

Approximately one year ago, I (Curle) asked the team about the possibility of using the then-mostly-unused Announcements channel on the Discord server for informing the community about major updates to Forge.  
That means; breaking changes, major changes and additions to the API, and simply being more transparent about the inner workings of the project and the update process.

At the time, it was decided that I may provisionally post any updates I wish to the channel, gague reception, and adjust accordingly.

This turned out to be a huge success.

## FUN

After the idea of full transparency and posting updates about API changes turned out to be a massive success, I created a small team dedicated to doing this, and called it the Forge Update Network (initialized to FUN, and with the original goal of being fully transparent; updating the community on everything that happens on the Forge "network".)

Initially, FUN consisted of just me and a few of the Moderators, who I shall not name here.

It, eventually, returned to being just me after a while - primarily due to lack of time from other members of the team, focussing mainly on the maintenance and moderation of the community.

However, it remained successful even with just me doing the work.

## Updates

After I and a few other members of the team (enormous credit to gigaherz, SizableShrimp and sciwhiz12) started taking over the process of updating Forge to newer versions of the game, we collectively redesigned and standardized the process between us, leading to lots of documentation, deep dives into obscure parts of the toolchain, and creation of new tools to verify that our work was being done properly.

Naturally, this led to us having lots of interesting tales to tell, and found ourselves having nowhere to tell them.

I proposed the idea of a Forge Blog some time after we updated to 1.18, simply because there were lots of obscure issues that led to interesting debugging sessions that I thought could be interesting to some of the more technical members of the community.

At the time, update was rather reluctant; our Forums technically had a blog feature, and it was rather unlikely to be used actively, so the upkeep and hosting costs weren't deemed worth it.

## Github Pages

For those unaware Github is a site where people can upload, manage and collaborate on code.

It also has a feature where you can feed it some static (AKA, not changing) web data, and it will host those pages on their own servers. You can even tell it to host the pages under your own domain name.

This, combined with a Static Site Generator (a tool that can create said static web data from simple markdown files) and Github Actions (a tool that can automatically run other tools when the github code is updated), we were able to set up a blog that is hosted and managed for us with no hosting costs, no upkeep, and no pain.

This unlocked a world of possibilities.

## Publishing

Since this blog is generated with Hugo, a static site generator, there is only one reliable way to tell when new posts are made.

RSS (Really Simple Syndication) is an xml file that other tools can look at to determine whether the content of a site has updated.

It is typically used with a Reader that can combine the content of multiple websites into an easy to read feed.

However, in this case, we use it to send out two webhooks; one to Discord (to replace the manual system of writing content in the Announcements channel) and one to Twitter (to be able to publish our posts to a much much wider audience).

We decided to do this after a conversation with some modders, when it was determined that despite the work that has gone into updating the community with regular announcements, it still wasn't reaching a wide enough audience for its intended purpose to work.

By consolidating all of the FUN announcements into one place, and automatically posting them to Discord (to keep the current system in place) and Twiter, we essentially triple the visibility of our posts, which can only increase over time as people retweet / share / subscribe to announcement channels. 

We hope that eventually, this will be able to keep everyone that uses Forge updated on everything we do via FUN.

## Personal Posts

Of course, this is a Blog, not an announcement feed.

The announcements are simply the secondary reason we have it.

The main reason is to share the aforementioned debugging tales, deep dives into obscure tools, and the intricate and interesting history of some of the tools we've created over the years.

We deeply believe that this blog will be of interest to a lot of community members.  
Doubly so, since we're going to allow community members to, should they desire, write articles for the blog too.

Simply get in touch with one of us (preferably Curle or cpw) and we'll get you sorted.

## Summing it up

This Blog will be dual purposed. We'll post regular updates on changes to the API (in a weekly-roundup manner) so that modders and users can keep up to date on new features and things that may affect them.

We'll also post personal tales and stories, in-depth explanations of sections of the API and the toolchain, and generally things that interest us and we think will interest you.

The blog has categories for each of these types of posts, so that you can filter things out and see what you want to see.

Each post will be published to Discord (taking the purpose of the current Announcements channel usage) and to Twitter.