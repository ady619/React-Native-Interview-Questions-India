# React-Native-Interview-Questions-India
React Native Interview Questions mainly asked by Indian Interviewers

# React Native Interview Questions and Answers

## Table of Contents

| No. | Questions                                                                                                    |
| --- | ------------------------------------------------------------------------------------------------------------ |
| 1   | [What is React Native?](#1)                                                              |
| 2   | [Why use React Native?](#why-use-react-native)                                                               |
| 3   | [What are the advantages of React Native?](#what-are-the-advantages-of-react-native)                         |
| 4   | [List the essential components of React Native.](#list-the-essential-components-of-react-native)             |
| 5   | [What are the cons of React Native?](#what-are-the-cones-of-react-native)                                    |
| 6   | [How many threads run in React Native?](#how-many-threads-run-in-react-native)                               |
| 7   | [What are props in React Native?](#what-are-props-in-react-native)                                           |
| 8   | [What are React Native Apps?](#what-are-react-native-apps)                                                   |
| 9   | [What are my options for storing data when using React Native?](#9)

<a name="1"></a>
1. ### What is React Native?

    React native is an open-source JavaScript framework designed by Facebook for native mobile applications development. It is based on a JavaScript library-React.
    
    React Native saves your development time as it enables you to build real and native mobile apps within a single language – JavaScript for both Android and iOS platforms, such that code once, run that on any platform, and the React Native App is ready for use with native look and feel.

3. ### Why use React Native?

    There is the following list of React Native features behind its use:
    - Easy to use.
    - Open-source framework
    - Cross-platform compatibility
    - Code Sharing
    - Use a common language – JavaScript for cross-platform development.
    - Faster Development
    - Saves Time and efforts
    - Gives Native look and feel

4. ### What are the advantages of React Native?

    - React Native is based on “Learn Once Write Everywhere” approach to equip developers with a tool that only needs to be learned once, just in a single language and then can be reused on both iOS and Android mobile platform.
    - React Native offers **cross-platform development** and a real experience to developers allowing them to build only one app with effectively 70% code sharing between different platforms.
    - React Native helps in **faster development.** Building one app instead of two using a common language gives speedier app deployment, delivery, and quicker time-to-market.
    - React Native exists with **essential components** for ending of native apps as the app development ends with native look and feel.
    - React Native has a **large community** of developers for its security. The developers are always ready to fix bugs and issues that occur at any instant. They improve the performance of React Native from time to time with the best practices possible.
    - React Native supports **Live and Hot Reloading.** Both are different features. Live Reloading is a tool that helps in compiling and reading the modified files. Hot Reloading is based on HMR (Hot Module Replacement) and helps to display the updated UI content.

5. ### List the essential components of React Native.

    These are the following essential components of React Native:

    - View is the basic built-in component used to build UI.
    - Text component displays text in the app.
    - Image component displays images in the app.
    - TextInput is used to input text into the app via the keypad.
    - ScrollView is a scrolling container used to host multiple views.

6. ### What are the cons of React Native?

    - React Native is still a new development platform as compared to iOS and Android platforms. It is still immature, i.e., in an improvement stage and impacting negatively on apps.
    - Sometimes, React Native built-in apps face performance problem if there is a requirement of advanced functionality. In that case, they don’t perform well as compared to native apps.
    - React Native has a steep learning curve for an average learner as it is not more comfortable in comparison to other cross-platform apps. It is because of existing JSX (JavaScript Syntax extension) in which HTML and JavaScript get combined and make learning challenging for average ones.
    - React Native is based on JavaScript library which is fragile and creates a gap in the security robustness. As an expert’s point of view, React Native is not secure and robust for building highly confidential data apps like Banking and Financial apps.

7. ### How many threads run in React Native?

    There are two threads run in React Native:

    - JavaScript thread
    - Main UI thread

8. ### What are props in React Native?

    props pronounced as the properties of React Native Components. props are the immutable parameters passed in Presentational Component to provide data.

<a name="9"> </a>
9. **What are my options for storing data when using React Native?**

**Async Storage** (formerly "built-in" to React Native, now moved on its own)

AsyncStorage stays local to the device, is unencrypted (as mentioned in another answer), goes away if you delete the app, but should be saved as part of your device's backups and persists during upgrades (both native upgrades ala TestFlight and code upgrades via CodePush).

Conclusion: Local storage; you provide your own sync/backup solution.

**redux-persist-filesystem-storage**
AsyncStorage has a default limit of 6MB on Android. It is possible to configure a larger limit (on Java code) or use redux-persist-filesystem-storage as storage engine for Android.
With react native, you probably want to use redux and redux-persist. It can use multiple storage engines. AsyncStorage and redux-persist-filesystem-storage are the options for RN.

SQLite

Other projects I have worked on have used sqlite3 for app storage. This gives you an SQL-like experience, with compressible databases that can also be transmitted to and from the device. I have not had any experience with syncing them to a back end, but I imagine various libraries exist. There are RN libraries for connecting to SQLite.

Data is stored in your traditional database format with databases, tables, keys, indices, etc. all saved to disk in a binary format. Direct access to the data is available via command line or apps that have SQLite drivers.

Conclusion: Local storage; you supply the sync and backup.

**Firebase**

Firebase offers, among other things, a real time noSQL database along with a JSON document store (like MongoDB) meant for keeping from 1 to n number of clients synchronized. The docs talk about offline persistence, but only for native code (Swift/Obj-C, Java). Google's own JavaScript option ("Web") which is used by React Native does not provide a cached storage option (see 2/18 update below). The library is written with the assumption that a web browser is going to be connecting, and so there will be a semi-persistent connection. You could probably write a local caching mechanism to supplement the Firebase storage calls, or you could write a bridge between the native libraries and React Native.

Update 2/2018 I have since found React Native Firebase which provides a compatible JavaScript interface to the native iOS and Android libraries (doing what Google probably could/should have done), giving you all the goodies of the native libraries with the bonus of React Native support. With Google's introduction of a JSON document store beside the real-time database, I'm giving Firebase a good second look for some real-time apps I plan to build.

The real-time database is stored as a JSON-like tree that you can edit on the website and import/export pretty simply.

Conclusion: With react-native-firebase, RN gets same benefits as Swift and Java. [/update] Scales well for network-connected devices. Low cost for low utilization. Combines nicely with other Google cloud offerings. Data readily visible and editable from their interface.

**Realm**

Update 4/2020 MongoDB has acquired Realm and is planning to combine it with MongoDB Stitch (discussed below). This looks very exciting.

Update 9/2020 Having used Realm vs. Stitch: Stitch API's essentially allowed a JS app (React Native or web) to talk directly to the Mongo database instead of going through an API server you build yourself.

Realm was meant to synchronize portions of the database whenever changes were made.

The combination of the two gets a little confusing. The formerly-known-as-Stitch API's still work like your traditional Mongo query and update calls, whereas the newer Realm stuff attaches to objects in code and handles synchronization all by itself... mostly. I'm still working through the right way to do things in one project, which is using SwiftUI, so it's a bit off-topic. But promising and neat nonetheless.

Also a real time object store with automagic network synchronization. They tout themselves as "device first" and the demo video shows how the devices handle sporadic or lossy network connectivity.

They offer a free version of the object store that you host on your own servers or in a cloud solution like AWS or Azure. You can also create in-memory stores that do not persist with the device, device-only stores that do not sync up with the server, read-only server stores, and the full read-write option for synchronization across one or more devices. They have professional and enterprise options that cost more up front per month than Firebase.

Unlike Firebase, all Realm capabilities are supported in React Native and Xamarin, just as they are in Swift/ObjC/Java (native) apps.


