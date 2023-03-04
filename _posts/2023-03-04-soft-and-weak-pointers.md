---
title: Soft and Weak Pointers
date: 2023-03-04 03:15:00 -500
categories: [devdoc, comparison]
tags: [development, gameplay, programming, documentation, unreal engine, c++, blueprint, cplusplus]
---

## **Soft** and **Weak** Pointers Unreal Engine
> A deep dive into the different soft and weak pointer types in Unreal Engine.

| ✔ Use these pointer | ❌ Do Not Use these pointer |
|-----------------|-----------------|
| **TSoftObjectPtr** | **FSoftObjectPath** |
| Used for referencing objects which might or might not be loaded via their path. Can point to actors in other levels even if they aren't loaded. Can be used with Asynchronous loading functions when pointing to assets (like meshes) to load them ad-hoc. Same as the "Soft Object Reference" blueprint variable type. | Used internally by the other pointer types ☝. Is slow as it doesn't cache the results. If set in Editor it will point to the UBlueprint class instead of the UBlueprintGeneratedClass, which is usually not what gameplay code wants. Makers of Editor Plugins might want that functionality though. |
| **TSoftClassPtr** | **FSoftClassPath** |
| Used for referencing class or blueprint types that might or might not be loaded. Once loaded it will give you a class type that you can create instances from. Can be used with Asynchronous loading functions to load them. Same as the "Soft Class Reference" blueprint variable type. | Same as FSoftObjectPath but with some helper functions related to loading classes. Mostly a legacy type now. |
| **TWeakObjectPtr** | **FSoftObjectPtr** |
| Used to reference already instantiated objects. Will resolve to null if the object gets destroyed or garbage collected. | Non-templated and non-BP exposed version of TSoftObjectPtr. |