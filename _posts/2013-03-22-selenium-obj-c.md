---
title: Objective-C Bindings for Selenium
layout: post
---

While I was working on an DOM inspector for Appium.app I encountered the problem that I needed to talk to Appium from Objective C. I scratched my head and though of how I might accomplish this. I code either write some weird private socket server in node or just use Selenium, only there were no objective c bindings for Selenium. Selenium seemed like the much more straightforward route to go.

My first instinct was to just write some javascript or python scripts that I could call from the app that use the existing webdriver bindings. TERRIBLE HACK... I know, but you have to remember Appium was founded on a spectatular compsition of great hacks. The first version of Appium was written in python and was able to control the iPhone simulator by writing files in a directory in a sequentially ordered fashion, each containing one command of raw javascript. A javascript file that was loaded by instrument would sit and wait for the next command file to come in and use the cat command to read it in. (No File I/O in instruments js, but there was that useful performHostTaskWithArguments command) All this of course after it authenticated the security dialogs using AppleScript UI automation.

Anyways, back to the task at hand. Since Appium is no longer a beautiful symphony of hacks, but a properly coded solution. So I though, how hard can it be to write remote webdriver bindings for Objective C. It didn't look so bad just about 80 or so different flavors of web requests, but is there any redeeming value to having objective-c selenium bindings exist?

"Would anyone other than myself use these bindings?" Then it occurred to me a half-dozen PHP bindings already exist, and if so many people want to write automation in PHP, it's probably because the developers want to code their apps and write tests in one language. Either that, or a lot of developers haven't been exposed to the finer things in life. (like Python)

Either way it finally made sense. Mobile developers write their apps in Objective C, why not write their functional UI tests in the same language. It's no worse than writing this stuff in PHP. They could even put these tests in their test projects in XCode and use existing unit test infrastructure with their Selenium automation. In about 3 days, it was all done, and now they finally do exist.

The binds are now available for download <a href="https://github.com/appium/selenium-objective-c">here</a>.

SERemoteWebDriver *driver = [[SERemoteWebDriver alloc] init],<br />
<a href="http://github.com/penguinho">Dan</a>
