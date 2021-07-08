---
layout: post
title:  "Cross-Platform Mobile Development"
date:   2021-07-06 00:11:06 +0530
author_profile: "Kalyan"
categories: android
background: '/assets/images/posts/cross-platform-dev.jpeg'
---

What is cross-platform mobile development? Is it writing in a single language and running it on both Android and iOS? Or is it writing common business logic in a common language and share with native platform code? Is it HTML/JS or C++ or can it be your regular kotlin and swift? Find out more about Cross-platform development, how it evolved over the years and what it means for Native Android or iOS developers.

Listen to the show here:
<iframe src="https://anchor.fm/reactivity/embed/episodes/Cross-Platform-App-Development-e13knph" width="100%" frameborder="0" scrolling="no"></iframe>

Let's talk about what, why, and how of cross-platform development. If you are new or switching your career to mobile development, you may have a question about what you should learn or begin with? Learn a single platform or both natively or choose a cross-platform solution. Remember whatever language or framework we use, we should maintain the standard and quality that we plan in our apps. 

`TLDR;` To give you a short answer, you should learn the platform natively that you want to develop apps on, even if you end up choosing a cross-platform solution. If you think otherwise or want to know in detail about my thought process, let me break this down beginning with how it all started.

The whole need for a cross-platform solution came into the picture to solve the problem of ease of maintenance and in some cases, try to keep the cost low. The case of ease of maintenance holds good to some extent but the second one may not be true. So with these two problems to solve and with available options at that time, anyone would choose a web-based solution. That is the first available cross-platform solution. `A Web App`.

### Web Apps
Web apps configured for mobile screens would definitely solve the problem but comes with their own set of problems especially distribution. There is no way to submit web apps to the stores. So the logical next step would be finding a way to pack a web app into a container and then publish them on the app stores.

### Cordova
That's how we got the famous `Cordova` framework. It basically solved the problem simple and straight and so it got its popularity paired with HTML5 adoption back then. If I remember correctly even the Facebook app chose this path. Of course, they regretted it later, but Cordova did its job pretty well both by providing a way to package a web app and most importantly APIs to access native features like location, camera, etc.

#### Ionic
Even though Cordova solved these two problems, a web app will be a web app. It doesn't feel native. So came the next set of evolutionary frameworks like `Ionic`. I had first-hand experience with Ionic. Back when I was starting to write mobile apps, Ionic seems promising. In addition to using Cordova as the way to build the apps, it provided styled components that look and behave like a native component. Even though Ionic did a good job in bringing the gap closer for a cross-platform solution, it is still a web app. Soon its popularity is clouded by React Native and the introduction of a concept called PWA - Progressive web apps. 

### React Native
React Native, a success story that we all know today is definitely an innovative solution that introduced the concept of `learn once and write anywhere` as opposed to write once and run anywhere. Its innovative solution of writing in JS and getting a performance closer to a native app and being backed by Facebook has just made React Native the popular option out there.

They introduced this technique where we write the app's UI and logic in JS and in runtime the framework translates not just the logic but also the UI into the `actual native platform-specific components`, thus giving better performance than just rendering the web pages. However, the bridge that translates or communicates between the JS and native layer is now the only bottleneck or the overhead that would stop it from matching the performance with a native app.

My personal experience is, I should say, not so good. I have tried it in very early days though. I was able to achieve my target but I had to swim through a sea of compatibility issues, faster releases, and not so well documented third-party plugins, and so on. If you get stuck in any build-related issue, that would be a whole new level problem to solve that would require editing the platform files. This used to happen a lot back then when there are some changes or updates to the native platforms or react native itself. This is just my opinion, I have seen many happy developers using React native.

`Native Script` is also something that does similarly by rendering JS as native components, but it wasn't adopted like React Native. I haven't tried it personally anyway, but it is worth mentioning it.

### PWA
Progressive web apps are just web apps but are tuned to be lightweight and mainly support offline features with service workers. With major adoption from google, they made it to mainline by adding an option to add these web apps to the home screen of your phone and give them an app icon just like a native app. PWAs are a quick solution that can be downloaded and run smoothly on a low-end phone with less bandwidth. There are many successful use-cases with PWAs like Flipkart, Uber, Airbnb, etc. They leveraged the lightweight aspect of PWAs and offered a mini version of their apps with limited features specifically for low-end devices.

### Flutter
While all this is happening, Google is working on another solution in a different way to solve this problem. Flutter. It is a cross-platform solution that follows the principle of `write once and run everywhere`. Flutter solves this by compiling the code into native arm binaries and then rendering them directly with their own rendering engine called Skia. Skia is used in some games as a graphics engine. This is both a pro and con in the sense that it opens up new possibilities in the world of cross-platform development and at the same time suffer from bigger app sizes. Another caveat that comes with flutter is the language Dart, it can be a separate learning curve from some. With the backing from Google and the speed at which Flutter is being adopted, it can reach different heights.

### Kotlin Multi-platform Mobile
The latest framework to join the race is Kotlin multi-platform mobile. This isn't our traditional solution of writing once or learning once to run everywhere. KMM has its boundaries clearly marked saying it is a solution to write your logic once in kotlin and link it with your natively written view layers for Android and iOS. The SDK then offers the ability to call the business layer functions from the native layer. Hence it is basically a native app with some added comfort. Personally for Android Devs, working with Kotlin will always be exciting. It is currently being actively developed and we have to see where it reaches.

#### Conclusion
Finally, it all comes to us, developers. `Bad code in a native app couldn't be better than a well-written app in a cross-platform solution and vice-versa`. However, the caveats are a bit less in native apps and hence you may get better performance out of the box.

So to answer my question, even if you are planning to develop a cross-platform app, you should have knowledge about how things work in the native layer to make the apps both beautiful and performant.

At the end of the day, these are the apps that run on mobile devices. And with the fast-moving ecosystem, it is essential to understand how things work in the native layer of the platform to leverage more of its new features. In other words, consider a scenario where you want to use a platform feature for which you don't have support in the cross-platform framework that you are using.

It is definitely a good time to build apps and start solving problems one at a time. Why I said good time is because of the recent announcement from Microsoft that `Android Apps can now be downloaded and run on Windows 11` via the Amazon app store which is available in the default windows store. This could be great news that your Macbooks, Chromebooks, and Windows can now run Mobile apps.

Oh! I almost forgot `Xamarin`. A fun fact, my first software project is a Windows Phone app written in C#. With my little experience in C#, Xamarin seemed a very good solution for writing cross-platform apps. But... you know what happened.

#### Show Notes:
Cordova: [https://cordova.apache.org/](https://cordova.apache.org/)

Ionic: [https://ionicframework.com/](https://ionicframework.com/)

React Native: [https://reactnative.dev/](https://reactnative.dev/)

Native Script: [https://nativescript.org/](https://nativescript.org/)

PWA: [https://web.dev/progressive-web-apps/](https://web.dev/progressive-web-apps/)

Flipkart's PWA: [https://medium.com/progressive-web-apps/building-flipkart-lite-a-progressive-web-app-2c211e641883](https://medium.com/progressive-web-apps/building-flipkart-lite-a-progressive-web-app-2c211e641883)

[https://developers.google.com/web/showcase/2016/flipkart](https://developers.google.com/web/showcase/2016/flipkart)

Flutter: [https://flutter.dev/](https://flutter.dev/)

KMM: [https://kotlinlang.org/lp/mobile/](https://kotlinlang.org/lp/mobile/)

Photo by <a href="https://unsplash.com/@altumcode?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText">AltumCode</a> on <a href="https://unsplash.com/s/photos/ios?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText">Unsplash</a>