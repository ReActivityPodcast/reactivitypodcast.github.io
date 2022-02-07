---
layout: post
date: 2022-02-07 19:00:00 +0530
author_profile: Kalyan
title: Android Security and User Privacy
categories: blog
background: "/assets/images/posts/android-security.jpg"

---

Security and User privacy are key aspects that will help a product or app succeed. In the case of mobile applications, while platforms do the heavy lifting in terms of security, it is also on us, developers, to secure our product and protect our user’s data. In this brief post, I will talk about what we as developers can do by leveraging platform-provided options properly to enhance the security of our applications.

Before we go further into the details, we have to understand that implementing the level of security depends on your use case. For example, a to-do app need not encrypt all the user’s tasks before saving them to disk. But, if it’s a payment application, it would be wise to save the user’s credit card information in a much more secure manner. With that said, let’s dive deep.

If you are interested in listening, here is the link to this episode:
<iframe src="https://anchor.fm/reactivity/embed/episodes/6-Android-Security-and-User-Privacy-e1dv81t" width="100%" frameborder="0" scrolling="no"></iframe>

# User Privacy
Let’s begin with User privacy and what we can do to ensure users’ data is secure and private. We need not worry much about this segment as this is something completely in our control. To simply put, if we don’t need it, we don’t access it. Secondly, by following the best practices suggested by the platform, we can ensure the users’ data is safe and gain the confidence of our audience.

## Some of the best practices in terms of privacy:
Let's see some of the best practices to follow for improving user privacy.
#### Keep an eye on when and how we access the user’s location.
Whenever we access the location, the user gets notified with an icon in the status bar and the latest versions of both Android and iOS offer options in settings to check which apps have accessed the device location recently. Unlike in the earlier versions, there is no playing around with a user location. Unless it’s a specific use case, we should avoid accessing the location. We should also evaluate the level of location granularity that our app needs. In most of the use-cases, coarse location access should be sufficient.

#### Pay attention to permissions
One of the key areas where we can gain user confidence is by requesting as minimum permissions as possible. As we keep updating the app with more and more new features, it is important to re-evaluate the permissions that are still relevant and drop the ones which we don’t need anymore. There are some interesting APIs that Android offers in Android 11 onwards, that can audit the data accessed by our apps and the third-party libraries that we include. Read more [Audit access to data | Android Developers](https://developer.android.com/guide/topics/data/audit-access)

#### Unique identifiers that we use to identify users or devices
It is a very common use case in our apps to track or identify a user or device that is used for various analytics. And some of us use the device’s built-in identifiers like IMEI and Serial numbers for this purpose. Of course, as we target Android 10 or higher, accessing them would throw a Security Exception. But in older versions, we should be aware of what’s private to a user and respect that privacy. Android does provide identifiers for nearly all the use cases that fall into these categories that are secure to use. For example, we should use an Advertising ID for user profiling or targeting ads. Android also offers a Secure Android ID to share state between apps that we own without requiring a user to sign in. For almost all the other use cases, we can generate a simple GUID and use it for other analytics purposes.

Apart from these, there are other things to keep in mind like:
- Letting the user know when we collect sensitive data that we intend to use for making the product better or anything similar.
- Nowadays, Android shows an indication in the status bar when the camera or the microphone is accessed. So we should ensure to end the recording sessions properly and it is wise to ask for permission only when a user accesses the feature that requires camera or microphone access.
- Last but not least, avoid logging private data in the logcat messages or the log files of your app.

These are some of the important and basic things to adhere to before publishing our apps to gain users’ confidence about their privacy.

## App Security
we have seen how we can improve user privacy in our apps, now let us focus on improving app security.

#### Secure your Network Connections
The first and foremost point that I want to discuss in this section is secure network connections. It’s 2022 and it is almost a sin to run your server or connect to a server that only offers HTTP endpoints. When services like Let’s Encrypt are available for free of cost, there is no reason not to enable SSL for your endpoints. It is very easy to monitor traffic with the plethora of tools available for free. In case you haven’t already, take a couple of days and enable SSL on your server. If the application’s security is crucial, we can also consider adding Certificate Pinning to avoid man in the middle attacks. Android also provides network security configuration that allows us to configure custom CAs and even self-signed certificates.
Read more: [Network security configuration | Android Developers](https://developer.android.com/training/articles/security-config#CertificatePinning)

#### Store sensitive data securely
For most of the use cases, we can save the data generated by the app in the internal storage of the device which is private and sandboxed to our app. A typical example of this would be our databases, cache directory and shared preferences. While in modern devices this is secure, a rooted device would give away this storage access to the user or the other apps. Hence we should consider encrypting sensitive data like access tokens and secrets. Jetpack provides an encryption library to encrypt both shared preferences and files and makes it super easy to implement.
Read more: [Security | Android Developers](https://developer.android.com/jetpack/androidx/releases/security)

#### Safeguard against Security Threats
While we are on the topic of rooted devices, let’s talk about what we can do on that front. Encrypting app’s tokens before storing them would reduce the risk in the case of rooted devices. However, if your application needs more security, say a banking application or an enterprise application, you would want to check if the device is safe to install your app. For this exact use case, Google offers a bunch of APIs under the SafetyNet Library. It has four different offerings:
- `Attestation API` for checking the device integrity. This API will not just check the root access status, but also does the other integrity checks like if the device has a custom ROM or the bootloader is unlocked etc.
- `Safe Browsing API` to check if any specific URL the app is connecting to is malicious
- `reCAPTCHA API` that helps in avoiding malicious traffic and avoid attacks like DDOS
- `Verify apps API`, which can check if there are any malicious apps on the device before enabling certain features of the app.

Overall this is a powerful library, solving these specific use cases that would be hard to achieve otherwise. Apps that need this level of secure environment can leverage this offering and improve their security.
Read more: [Protect against security threats with SafetyNet | Android Developers](https://developer.android.com/training/safetynet)

#### Protect against Reverse Engineering
One last topic that I want to discuss is about keeping sensitive data in the code. We must be aware that reverse engineering is relatively easy on Android than on the other platforms. So we should keep in mind that our code would be available for other developers to read. But we can make it difficult to break into. The first step in this direction would be obfuscating our code. By [enabling R8 in our project](https://developer.android.com/studio/build/shrink-code) we can not only obfuscate the code but also shrink unused code and resources and optimize the code to reduce the DEX file size. I have also seen developers who put sensitive data in the native C++ layer of the code which makes it, even more, harder to reverse engineer. But the best way is to avoid keeping sensitive data in the code.

These are some of the important topics that can improve the security of the app. There is an extensive guide on the Android developers portal about all the best practices for user privacy and security. It offers other suggestions like granting one-time permission while sharing a resource between apps, how to use new scoped storage access and many more. [Make sure to read this section for more tips.](https://developer.android.com/topic/security/best-practices)