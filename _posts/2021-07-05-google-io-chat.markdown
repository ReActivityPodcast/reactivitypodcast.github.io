---
layout: post
title:  "Google IO 2021 chat"
date:   2021-07-05 10:11:06 +0530
author_profile: "Kalyan"
categories: android googleio
background: '/assets/images/posts/google-io-chat.jpg'
---
Every year Google IO brings us a ton of content, something for us to learn and try for the whole next year. It is a special event, specifically for Android Developers.

Listen to the episode here:
<iframe src="https://anchor.fm/reactivity/embed/episodes/Google-IO-2021-Highlights-An-Android-Developers-Perspective-e1345ju" width="100%" frameborder="0" scrolling="no"></iframe>

As usual, which has been a norm for the last couple of years, this year's conference is majorly focused on Machine learning advancements at Google. However, `Android` took center stage and a lot of updates compared to last year, Android 12 being the biggest update.

### Android 12
- New UI is the biggest update. The design team at Google has done a really good job in designing the system. They have introduced a rich color palette that can be changed to make the look and feel of your device unique. They took it to another step with generating those colors for you based on the wallpaper for Pixel devices.
- After UI, the next focus has been on privacy. There are a couple of new enhancements in this aspect. First being a Privacy Dashboard. In Android 12, you can find a dashboard in the system settings where you can glance at the privacy-related permissions that have been accessed by other apps recently. This includes location, camera, microphone access, and more.
- These are definitely welcoming changes from the end-user perspective, and for developers, this means that we should respect the privacy changes and access them only when necessary.
- Speaking of developer changes, in Android 12, there will be an option to select an Approximate location instead of a precise location. When you request location permission, check what has been granted by the user and provide the experience in your app accordingly. Also, there will be an indication of microphone and camera access and a toast on reading the clipboard data are some updates that focus on the fact that it is a good time to clean up those unwanted permissions and improve the standard of Android apps in terms of privacy.

<!-- <img src="/assets/images/posts/location-permissions.png" height="100%"/> -->
![Approximate Location](/assets/images/posts/location-permissions.png)


### Private Compute Core
When I first heard about this in the keynote, I pictured dedicated hardware to store and process sensitive data. But it is more like a place or a layer in the operating system that is isolated technically from the rest of the system, other apps, and even from the network. Let me explain it with an example. Take the smart reply feature in Messages or Gmail, to achieve this the app needs to know the conversation that is happening on the screen. Imagine if this feature needs to be built by an app. If you think of sending this data to your server and then running your ML model on it, then that is not a good idea in terms of user privacy. Of course, most of the services still do it, there have been some efforts in bringing the ML inference layer onto the device, in this case, the data won't leave your device, at least technically, and you can get the benefits like a smart reply. So with private compute core, this has been taken to another level where the data is sandboxed and the APIs to access the data are secured and open-sourced. This way your private data will not be even shared with the apps or the keyboard that provide this functionality.

### Widgets
Widgets are not new to Android. They may be new to iOS but they have been around since 2008 in Android. In Android 12, the widget picker has been redesigned and is a bit similar to what we have in iOS 14. They can now show a preview of the widget's look and feel before dragging them onto your home screen. Widgets in Android are not just views to display quick, `glanceable information`, they can also be interactable. My favorite feature in widgets this year is the `improved discoverability` so that widgets can show up in search and google assistant's panel. I was excited to see the demo with widgets done with an e-commerce app. So when you ask google assistant to order something from an app, it can display the info in a small widget and then place the order directly from there. This opens up a new way for your audience to interact with your app. So make sure to focus on those long-pending widget-related backlog items. As of today, we need to write UI for widgets in XML, however, there has been a quick preview shown about the version of widgets written with Jetpack compose. So another reason to try them out.

Another API caught my eye for audio-coupled haptic playback. You may have noticed subtle haptic feedback in iOS apps at the places like, say when your order is placed successfully. We can do that in Android easily now with this new API. This will be very useful in use cases as a successful purchase or an achievement unlock in your apps or games. These kinds of subtle things make a lot of difference in user experience.

### Android Studio
Android Studio's naming convention is now changed to names! Arctic Fox is the first release with this mane and Bumble Bee to follow. Both are available in Beta and Canary channels to try out today. They come with many features like better support for Jetpack Compose, improved build performance, built-in accessibility scanner to name a few.

### Kotlin
Coming to Kotlin, it always start with throwing some stats about the adoption of Kotlin in top apps on the play store and the adoption within google.

`KSP: Kotlin Symbol Processing` - a new annotation processor that speeds up build speed. The idea behind KSP is to replace KAPT, the current annotation processor that we use today in Kotlin apps. Unlike KAPT which generates intermediate Java stubs, KSP parses Kotlin code directly. This is a welcoming change as more and more libraries of jet pack uses more annotations. So if you are building any library that uses annotation processing then look out for KSP.

Another important announcement is that LiveData will be deprecated soon in the favour of another Kotlin API Stateflow. I personally didn't get a chance to try Stateflow APIs yet, maybe will try it out and share my thoughts on that later.

### Jetpack Compose
When it comes to announcements, the bigger one is that Jetpack Compose is moving to a stable release this July after almost two years of active development. Looks like the Android developer challenge that happened a couple of months is in fact to prep up devs into moving to Compose.

### Foldable devices
There are new APIs making it easy to support UI for different screen sizes, but I am not sure how many teams are currently planning to support foldable devices, as there are not many devices on the market as well. However, if we plan the UI elements with built-in support provided, in the beginning, it would be very minimal to no effort to migrate them for foldable devices if need be. With the support of Android apps on Chrome OS, sooner or later we may need to support different screen devices based on adoption.

### Wear OS
Wear OS updates has been my personal favorite. I have been waiting for a couple of years now to see an update for Wear OS. I used to use Moto 360 watch and I loved it. But there have been no significant updates to the Android Watch ecosystem since the initial releases and no doubt it is because of diversification in manufactures and their own flavors of Android for watches. With no major updates over the years, many users like me were forced to use the Apple Watch. To me, a smartwatch should be a health monitoring device. Of course, other features like notifications, taking calls, or controlling music are a bonus. This is just my opinion, you may have a different view. Either way, I think you would agree to have health monitoring features in addition to your favorites.

This year to my surprise, Google took an additional step and managed to bring in a `Unified platform partnering with Samsung` bringing in the sensor technology accuracy and battery optimization to Wear OS. Jetpack now includes APIs for Wear OS as well. What's cool is to see support in Emulator to simulate heart rate sensor data.

### ML on Android
Google always has a special spot on stage for ML. When it comes to ML on Android, there is an interesting announcement. Google has noticed that many apps have started integrating ML models in their apps, so they have announced a built-in updatable ML inference model that comes as part of Google Play Services. This includes a TensorFlow lite module and standardized NN APIs that take advantage of a dedicated NN core in modern chips.  I guess this model would be for common tasks like translation, live captions, handwriting, etc. On-device ML, I mean inference, of course, would play a crucial role going forward as privacy becomes more and more important in the Android ecosystem.

These are some of the updates from Google IO this year and we have a whole year ahead of us to try them out. I will make sure to add the links to the topics that we have discussed in today's episode in the show notes.

Before we wrap up this episode make sure to follow us on twitter at `@reactivitypod`. If you want to ask me anything or want to hear about some of your favourite topics make sure to tweet us with hashtag `#AskReactivityPod`. Alright! catch you all next week.

#### Show Notes:

Android 12: [https://developer.android.com/about/versions/12/features](https://developer.android.com/about/versions/12/features)

Widgets: [https://developer.android.com/about/versions/12/features/widgets](https://developer.android.com/about/versions/12/features/widgets)

Android Studio: [https://developer.android.com/studio/preview](https://developer.android.com/studio/preview)

KSP: [https://github.com/google/ksp](https://github.com/google/ksp)

Wear OS: [https://developer.android.com/wear](https://developer.android.com/wear)

ML on Android: [https://developer.android.com/ml](https://developer.android.com/ml)


Photo by <a href="https://unsplash.com/@chuttersnap?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText">CHUTTERSNAP</a> on <a href="https://unsplash.com/s/photos/google-conference?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText">Unsplash</a>
  