---
layout: post
title: "Xcode-select"
date: "2018-04-21"
categories: 
  - "xcode"
tags: 
  - "ios"
  - "swift"
  - "xcode"
image: /images/2018/04/mac-xcode.jpg
---
![]({{page.image}})


I've been learning some Server Side Swift with Vapor this week thanks to [Paul Hudson's awesome book](https://www.hackingwithswift.com/store/server-side-swift). Within about 10 minutes I learnt something which had nothing to do with Vapor, which is a good reminder that often it’s the extra bits and pieces you collect along the way that makes learning a new skill so beneficial.

As soon as I started I got a load of build errors like this one when running **xcode build** from terminal.

This is because Vapor 3.0 requires Swift 4.1 but I am currently using Xcode 9.1 (Swift version 4.0). I have a few different Xcode versions installed as always (the current App Store version and the latest Beta at least) and when I was running **xcode build**, the current App Store version was the one being used.

That's where **xcode-select** comes in because it enables you to switch versions. Pretty handy!

To install it you run xcode-select --install, then -print-path shows the current Xcode version being used, and -switch enables you to switch to a different version

{% highlight console %}
$ xcode-select --install
{% endhighlight %}

{% highlight console %}
$ xcode-select -print-path
/Applications/Xcode.app/Contents/Developer
{% endhighlight %}

{% highlight console %}
$ xcode-select -switch /Desktop/Xcode\\ 9.3.app/Contents/Developer/
{% endhighlight %}

(You may need to use **sudo** for some of these commands)

It's then really easy to just switch back to the main Xcode version when you need to:

{% highlight console %}
$ sudo xcode-select -switch /Applications/Xcode.app/Contents/Developer/
{% endhighlight %}

And now I can get on with learning more Vapor. I'm really enjoying it so far and am thinking of re-building this blog with it which should be fun!
