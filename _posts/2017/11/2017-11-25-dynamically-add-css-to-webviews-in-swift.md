---
layout: post
title: "Dynamically adding css to WebViews in Swift"
date: "2017-11-25"
image: /images/2017/11/colouring-pencils.jpg"
---

This week, I needed to figure out how to dynamically add css to a webView in iOS and it was much easier than I thought it would be.

All you need to do is make use of the webViewdidFinish function in the WKNavigationDelegate and evaluateJavaScript

{% gist c3163d98822b6bc4c3edb16943c684c1 %}

This code will change the background colour of the webpage you are displaying to red.

To show how this works, I created a simple sample app with a series of buttons with colour choices on:

![](/images/2017/11/view.png)

Clicking on any of the buttons takes you to a webView which displays www.google.co.uk but the background colour of the webpage changes depending on the button chosen. So if you click on green you're taken to this page:

![](/images/2017/11/webView-.png)

To do this, in the ViewController I added an IBAction which performs the segue when a button is tapped. The button text is then passed through to the WebViewController:

{% gist 83db251c9b6a7dc5423bdb854615932d %}

In the WebViewController there is a function getHexColour which determines the hex code colour based on the colour set in the segue.

Then in webViewDidFinish I created the css and JavaScript and applied that to the webView using the evaluateJavascript function:

{% gist 3b8f9216664dc6b51f67229dc0266e7c %}

Here's a link to the sample project code: [https://github.com/Ceri-anne/WebViewCss](https://github.com/Ceri-anne/WebViewCss)
