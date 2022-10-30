---
title: BP vs C++ Unreal Engine
date: 2022-10-22 03:15:00 -500
categories: [devdoc, comparison]
tags: [development, gameplay, programming, documentation, unreal engine, c++, blueprint, cplusplus]
---

## **Comparison** b/w Blueprints and C++

| Blueprints      | C plus plus     |
|-----------------|-----------------|
| No Codding required | Must have basic information about programming|
| **Pros** | **Pros** |
| Bit slower | Greater flexibility |
| Quicker to create new game  | Execute much quicker |
| Best for Game Designer | Best for Game Programmers |
| **Cons** | **Cons** |
| Messier | It is easier to make mistakes |
| Harder to troubleshoot errors and crashes |  |

## C++ vs Blueprints according to **Epic Games**

* C++
    * **Faster runtime performance** Generally C++ logic is significantly quicker than Blueprint logic, for reasons described below.
    * **Explicit Design** When exposing variables or functions from C++ you have more control over exposing precisely what you want, so you can protect specific functions/variables and build a formal "API" for your class. This allows you to avoid creating overly large and hard to follow Blueprints.
    * **Broader Access** Functions and variables defined in C++ (and exposed correctly) can be accessed from all other systems, making it perfect for passing information between different systems. Also, C++  has more engine functionality exposed to it than Blueprints.
    * **More Data Control** C++ has access to more specific functionality when it comes to loading and saving data. This allows you to handle version changes and serialization in a very custom way.
    * **Network Replication** Replication support in Blueprints is straightforward and is designed to be used in smaller games or for unique one-off Actors. If you need tight control over replication bandwidth or timing you will need to use C++.
    * **Better For Math** Doing complicated math can be difficult and somewhat slow in Blueprints, so consider C++ for math-heavy operations.
    * **Easier to Diff/Merge** C++ code and data (as well as config and possibly custom solutions) is stored as text, which makes working in multiple branches simultaneously easier.
* Blueprints
    * **Faster Creation** For most people creating a new Blueprint class and adding variables and functions is quicker than doing something similar in C++, so prototyping brand new systems is often faster in Blueprint.
    * **Faster Iteration** It is much quicker to modify Blueprint logic and preview inside the editor than it is to recompile the game, although hot reload can help. This is true for both mature and new systems so all "tweakable" values should be stored in assets if possible.
    * **Better For Flow** It can be complicated to visualize "game flow" in C++, so it is often better to implement that in Blueprints (or in custom systems like Behavior Trees that are designed for this). Delay and async nodes make it much easier to follow flow than using C++ delegates.
    * **Flexible Editing** Designers and artists without specific technical training can create and edit Blueprints, which makes Blueprints ideal for assets that need to be modified by more than just engineers.
    * **Easier Data Usage** Because storing data inside Blueprint classes is much simpler and safer than inside C++ classes; Blueprints are suitable for classes that closely mix Data and Logic.

> **References:** https://docs.unrealengine.com/4.27/en-US/Resources/SampleGames/ARPG/BalancingBlueprintAndCPP/

<script src="https://utteranc.es/client.js"
    repo="muhammadmoizulhaq/devdoc"
    issue-term="pathname"
    theme="github-dark"
    crossorigin="anonymous"
    async>
</script>