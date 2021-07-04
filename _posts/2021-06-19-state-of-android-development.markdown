---
layout: post
title:  "State of Android Development"
date:   2021-06-19 12:11:06 +0530
author_profile: "Kalyan"
categories: android
---
Listen to this episode here:

<iframe src="https://anchor.fm/reactivity/embed/episodes/State-of-Android-Development-e12m3ec" width="100%" frameborder="0" scrolling="no"></iframe>
One of the fast-changing fields of the software industry is mobile development. What I mean by fast-changing is that the way we design or architect our apps, the tools or libraries that we use and for that matter even the platform provided options for building these apps change very often.

In addition to that, every year these events like Google IO or WWDC bring a lot of new things.

I still remember those days when we created a new activity for each screen and made every other class a “parcelable” just to pass around as we like and call it a day. Those are the early days of android development where there are just a few devices and not many apps on the store as well. Also, there is no dedicated IDE to write android apps. We used to write all the logic that we have in the activity class and link it to the XML behind it to render the UI. I mean those worked just fine, of course, until your app became bigger and complex. At some point, it just gets harder and harder to maintain the code and fix the bugs. Over a decade, both the platform and apps have evolved so much that we can’t keep creating a new activity for everything. Because, these days we have to support features like widgets, deep links, instant apps, sharing and switching between apps, gestures and many more.

After those activity days came the most dreaded fragment days. In a way, these fragments are like a double-edged sword. If used properly, we can achieve things that are not possible with just activities alone. But at the same time, it was harder to use them properly and run into a new type of bugs. These fragments stayed for quite a while before the android team started to bring structure to what we have today. Also, back then there was no official guide on structuring the android app.

Around the same time, the awesome community started helping out with their own opinionated guides and frameworks. Soon we had an open-source library for everything. Picasso for Image loading, okhttp and retrofit for network, fastadapter that made working with recycler views a lot easier, Airbnb used their own deep linking framework called deep link dispatch, Uber did their own architecture library called RIBs, and Realm DB too, that made it super easy to use the database when compared to all the boilerplate that came with Content providers and Cursors with the platform provided options. These are some of the frameworks that I can think of at the top of my mind but I am sure that every one of us had our own favourites.

But all those days are way behind us when the Android team at Google introduced the Architecture components which they now call Jetpack. And basically, it changed everything. Suddenly we all got a standard way or a pattern to write our apps rather than getting inspired about an architecture that we heard about... at a meetup to which we can’t migrate our own apps.

But to be honest, even those new architecture components took their own sweet time to become mainstream. I remember how badly I want to use them but they are still in the alpha or preview phase to which I cannot justify being used in production applications.

Out of all the architecture components, in my opinion, Room and ViewModels were the much-needed ones. Other frameworks in the architecture components were also great, but these two are the ones that were easily adopted into every app that uses a database and want to bring structure to the code.

I remember around the same time came the first-class support for Kotlin which is again, hands down one of the best things that had happened to Android development. It just improved the developer productivity by making the code less verbose and less error-prone to common mistakes. And without much hesitation, many apps switched to Kotlin.

Later google started bringing everything under one umbrella with Jetpack and AndroidX. This specific change has added much-needed version management for the libraries that the android framework provide. Along with this versioning, they have also moved the commonly used classes like activity and fragment into these components and made them the defaults so that they can be updated regardless of the platform updates.

While we are still adapting to the shiny new architecture components,

the new kid on the block has already arrived, Jetpack Compose. Compose is essentially an entirely new way to write an app. We need to have a mental model of the state of the app because it is the state that drives the entire UI of your app. This model is not new and we have seen a similar style of writing apps in other frameworks like react, flutter and even SwiftUI. But it is still in its early phases and may take a little while more to become mainstream.

So the future is definitely bright. But one thing to remember is that we cannot just use or try everything that comes out on day one. We often tend to see on Twitter and other places people sharing their experiences with the new shiny stuff and sometimes we get demotivated about not trying it already. I used to be such a person early in my career. But things have changed. You need not try all the new things that come not just on the first day but it is okay to not try them even for the next few months. It takes a while for any new framework to come out of the alpha or beta phase. Remember compose was out for almost a year and it is still in the beta releases. Of course, if you have some time, you could always try them out, submit the feedback and improve these tools. But that is totally up to you.

Okay, so with that said, if I am starting a new project today what would I use?

Even though I had to say the classic answer “It depends”, I wanted to share my thoughts on this.

If I am starting a new side-project that is, my own app or an app for trying something, then I would definitely start with Compose along with a new navigation library, room as my go-to option for local storage, hilt for dependency injection, datastore for storing shared preferences and all the shiny stuff. But if it is at my work, I would rather stick to XML for UI, view models for maintaining my state and all the other tested stable stuff.

But either way, I would stick to the guidelines suggested in the developer portal. It is mature enough to stick to the basics and make life easy rather than running behind every new 3rd party library.

With that said, I would like to wrap up this episode. You can find the links to the frameworks that we have discussed in the show notes of the episode. Happy coding and catch you all in the next episode.

If you like the episode, make sure to subscribe to the show on Google podcasts or Spotify or Apple podcasts.

I almost forgot to say.. Hope you are still using the async task for the crucial background tasks in your app.

Show notes:

[https://developer.android.com/jetpack](https://developer.android.com/jetpack)

[https://github.com/airbnb/DeepLinkDispatch](https://github.com/airbnb/DeepLinkDispatch)

[https://github.com/uber/RIBs](https://github.com/uber/RIBs)

[https://github.com/mikepenz/FastAdapter](https://github.com/mikepenz/FastAdapter)
