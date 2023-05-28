---
layout: post
title: "Understanding Map functions in Swift"
image: /images/2018/05/map.jpg
date: "2018-05-08"
categories: 
  - "development"
  - "swift"
tags: 
  - "functional"
  - "ios"
  - "map"
  - "swift"
---

In Swift we have **`map`**, **`flatMap`** and now **`compactMap`**. What do each of these functions do and how can we use them? Let's have a look at **`map`**...

## Part 1:  Map

The **`map`** function takes a collection (often an array) and a function, and returns an array of items from the collection with the function applied to each item:

![](/images/2018/05/map-diagram.png)

So for example, we could take an array of integers and a function which multiplies integers by 2:

{% gist d6f72acf1865120c19edd73e638a35c3 %}

Or given a list of names, we could capitalise them all:

{% gist 12ce73048961749a7e698d53d34e85fe %}

\[NB: If the curly brackets or $0 notation are not familiar then it's worth reading up on [closures](https://developer.apple.com/library/content/documentation/Swift/Conceptual/Swift_Programming_Language/Closures.html) before continuing\]

The same result can be achieved by looping through each element in the array as follows:

{% gist  2ef6b1bb3f6e3da5cbb8b0c14aa8b0ab %}

So why use the map function?

- **`map`** is **declarative**. We are **declaring** what we want the code to do, rather than **how** we want it to do it **(imperative)**. The code is therefore declaring our intent, so should be clearer and easier to understand.
- With **`map`** we could declare the resulting array with**`let`** whereas with a loop we need to use **`var`.**  If we don't want this array to change after we've made it then this is safer code.

**Next up `flatMap`... coming soon!**
