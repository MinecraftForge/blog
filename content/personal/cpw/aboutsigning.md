title: "About signing"
date: 2023-06-29T13:10:31-04:00
draft: true
categories:
author: cpw
summary: "signing jars"
description: "about signing jars"
---
# About JAR signing 
I'm writing this post to try and clear up some misconceptions about jar signing. What can it do, what can't it do, why do we recommend it. Finally, I'll try and put together some resources for getting started. 

## What is JAR signing?
Jar signing is the act of generating a cryptographic signature for each member of a jar file. It dates to the beginning days of the Java ecosystem and is widely used by all teams creating Java distribution artifacts. 

If you recall the early days of the Minecraft modding world, you'll remember the instruction to "delete meta-inf" from the Minecraft jar file to get modding to work. This was actually deleting the Minecraft jar's signature data, so the Java virtual machine (JVM) could no longer verify that the code was created by and still the same as, what Mojang had built and signed. This is one of the key benefits of jar signing, it can be enforced by the JVM, so you KNOW that the code you're running is as it was when it was signed.

### Hang on, how does modding work these days then?
Well,  through careful use of the classloading mechanisms that check signatures, we can still CHECK the signatures before going on to carefully modify the code that actually runs. The running code isn't quite what was signed, but we're in control so we can manage it.


more to come.
