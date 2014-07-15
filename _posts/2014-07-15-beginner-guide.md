---
title: A Beginner's Guide to Appium
layout: post
---

While it can appear daunting at first, the steps required to set up and use Appium are actually quite simple. I recently set out to develop a test for an application called Cheddar (https://github.com/nothingmagical/cheddar-ios), and having never worked with Appium before, I went through quite a bit of the setup that many struggle with. This guide will show you how I went about setting up Appium, as well as how I finally wrote and executed my tests.


<u>Setting Up</u>

This stage can actually be incredibly simple. Instead of installing different dependencies, I just downloaded the Appium app (https://bitbucket.org/appium/appium.app/downloads/appium-1.1.0.dmg) and cloned the repository of the app I want to test. 

After launching the Appium app, click on the Apple icon. The app I am running is for IOS, so I want to set up my client to run IOS apps.

<img src="https://raw.githubusercontent.com/appium/blog/gh-pages/_posts/images/2014-07-15-img1.pngf">

Then, put in the location of my .app file. If you build your app for release or archiving, you can always find your .app file in ~/Library/Developer/Xcode/DerivedData/{app name}/Build/Products

<img src="https://raw.githubusercontent.com/appium/blog/gh-pages/_posts/images/2014-07-15-img2.pngf">

Appium is now set up! Wasn’t that easy?


<u>Building The Test</u>

This part is very dependent on how you wish to write your test, but I’ll briefly take you through my own process.

I decided to write my test in Ruby. As you can see, I begin my test with the requirements needed to run the file and information about the device I want to work off of. I also put in the path of the app I’m testing in my code as well. This is always good practice for your tests.

<img src="https://raw.githubusercontent.com/appium/blog/gh-pages/_posts/images/2014-07-15-img3.pngf">

Important tip: you can actually use the Appium inspector to find the xpath of all items within your app. You can also use it to record different actions, practically writing your code for you! The inspector can be used after you hit the launch button on the main appium window. Once the Appium server is launched, hit the spyglass to the left of the launch button to begin using the inspector.

<img src="https://raw.githubusercontent.com/appium/blog/gh-pages/_posts/images/2014-07-15-img4.pngf">

<u>Running The Test</u>

The most crucial part of this step is remembering that the test works off of the Appium server. You can’t run your Appium test without running the Appium server first, so make sure that you launch the server before trying to start your test!

First, click on the “launch” button on the Appium client to get started.

<img src="https://raw.githubusercontent.com/appium/blog/gh-pages/_posts/images/2014-07-15-img5.pngf">

Then, navigate to the location of your test in the terminal.

<img src="https://raw.githubusercontent.com/appium/blog/gh-pages/_posts/images/2014-07-15-img6.pngf">

After that, launch the test using the library you decided to write with. Since I wrote my test in ruby, I used the command “rspec test.rb” to launch my test.

<img src="https://raw.githubusercontent.com/appium/blog/gh-pages/_posts/images/2014-07-15-img7.pngf">

Then, just sit back and watch Appium do the rest!

<img src="https://raw.githubusercontent.com/appium/blog/gh-pages/_posts/images/2014-07-15-img8.pngf">

<a href="http://github.com/austenke">Austen</a>
