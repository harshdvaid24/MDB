
# react-native-template

[![Build Status](https://travis-ci.com/osamaq/react-native-template.svg?branch=master)](https://travis-ci.com/osamaq/react-native-template)
[![npm downloads](https://img.shields.io/npm/dt/@osamaq/react-native-template.svg)](https://www.npmjs.com/package/@osamaq/react-native-template)
[![npm version](https://img.shields.io/npm/v/@osamaq/react-native-template?color=44BC1C)](https://www.npmjs.com/package/@osamaq/react-native-template)

<p align="center" >
  <img
    height="480px"
    src="docs/assets/preview.png"
    alt="Template landing screen preview"
  />
  <img
    height="450px"
    src="docs/assets/reactotron.png"
    alt="Reactotron preview"
  />
</p>

<br/>

Preconfigured with

- TypeScript
- [axios](https://www.npmjs.com/package/react-native-axios) as data fetcher.
- [Redux](https://redux.js.org/introduction/getting-started) for global state.
- [Redux Thunk](https://www.npmjs.com/package/redux-thunk) for complex background thread-like work.
- [React Navigation](https://reactnavigation.org/) (**v5**) for navigation.
- [Reactotron in Flipper](https://shift.infinite.red/better-react-native-debugging-with-reactotron-in-flipper-6b823af29220) integration for debugging.
- [react-native-svg](https://github.com/react-native-community/react-native-svg) because svg.
- [react-native-config](https://github.com/luggit/react-native-config) to manage separate environments (dev, staging, production).
- [Reanimated](https://software-mansion.github.io/react-native-reanimated/) for animations.
- [Redash](https://wcandillon.github.io/react-native-redash/) its lodash for animations.
- [AsyncStorage](https://github.com/react-native-community/async-storage) you're gonna install it anyway.
- [FastImage](https://github.com/DylanVann/react-native-fast-image) its more performant
- [Detox](https://github.com/wix/Detox) for e2e.
- [Mirage JS](https://miragejs.com/) the easiest way to mock APIs.
- [Fastlane](http://fastlane.tools/) for automation.
- handy npm scripts.

## Contents

- [Documentation](#documentation)
- [Getting Started](#getting-started)
- [Optional Steps](#optional-steps)
- [Credits](#credits)

## Documentation

- [Libraries](#libraries)
- [Directory Structure](#directory-structure)
- [Quick Overview](#quick-overview)
- [File Walkthrough](./docs/file-walkthrough.md)



## Libraries

Let's briefly go over the benefit of each library included in this template.

### TypeScript

For type safety ¯\\_(ツ)_/¯

But in all seriousness, if you are considering this template I assume you are a TypeScript fan. If you happen to be a JavaScript user, this template might be overwhelming. 



### axios

-   Make  [XMLHttpRequests](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest)  from the browser
-   Make  [http](http://nodejs.org/api/http.html)  requests from node.js
-   Supports the  [Promise](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)  API
-   Intercept request and response
-   Transform request and response data
-   Automatic transforms for JSON data
-   Client side support for protecting against  [XSRF](http://en.wikipedia.org/wiki/Cross-site_request_forgery)

### Redux

I'm happy using Redux Toolkit. It's a lot more concise now and I enjoy the redux ecosystem of plugins.

Redux for global state. And sometimes React Navigation can be used to send data to the next screen. I try to leverage these two before reaching out to global state.

### Redux Thunk

Redux Thunk [middleware](https://github.com/reactjs/redux/blob/master/docs/advanced/Middleware.md) allows you to write action creators that return a function instead of an action. The thunk can be used to delay the dispatch of an action, or to dispatch only if a certain condition is met. The inner function receives the store methods `dispatch` and `getState` as parameters.


### React Navigation

It is the most popular navigation library. For most apps, this is the best choice.

### Reactotron/Flipper

Using this template there will be two main deubgging tools in your toolbelt. Reactotron and Flipper.

I mainly use Reactotron for reading API calls, asyncstorage operations, redux actions etc. It organizes everything in a neat way. It also has a killer image overlay feature, which allows you to get the UI design pixel prefect.


### react-native-svg

Prefer using SVG over images all the time (remember to optimize your SVGs).

### react-native-config

If you have different development, staging and production variables, this library is very helpful. It allows you to declare environment variables that can be accessed by all 3 sides (android, ios, JavaScript).


### Reanimated/Redash

Necessary when creating complex gesture based animations that are highly performant.

### AsyncStorage

For caching simple data such as user perferences.

### FastImage

Drop in replacement for the `<Image/>` component. I've found this to give a performance boost on android when rendering many images.

### Detox

For end-to-end testing.

### Mirage JS

Mirage is an in-memory server for intercepting API calls and returning whatever data you want. Very useful for developing before the backend is deployed, and for confirming how the app reacts to different API call outcomes.

### Fastlane

Fastlane community has an endless amount of mobile development automation plugins. I currently use it mainly for [automatic versioning](https://osamaq.com/automatic-versioning-for-react-native-apps/), and often for deploying to Microsoft's App Center in [one command](https://github.com/osamaq/reactnative-fastlane-appcenter).

This template also has a [fastlane command](https://github.com/osamaq/react-native-template/blob/acc4f4ab117bee099a531ad44be1130f9d24df69/template/fastlane/Fastfile#L203) for adding version badges to app icons. Useful outside of production as it makes it easier for QA to tell the app version.

<div align="center">
    <img src="docs/assets/ic_launcher.png" alt="App icon with version badge" width="20%">
</div>

---

> _If you appreciate those libraries and find them useful, please consider supporting them._

## Directory Structure

```
root
├── __tests__
├── android
├── e2e
├── fastlane
├── ios
├── scripts
└── src
    └── common
    |   ├── assets
    |   ├── components
    |   ├── exceptions
    |   ├── helpers
    |   ├── hooks
    |   ├── theme
    |   └── types
    └── features
    |   ├── error-boundary
    |   ├── home
    |   ├── landing
    |   └── navigation
    └── redux
    |   ├── middleware
    |   └── slices
    └── services
        ├── cache
        ├── navigation
        └── network
            ├── github
            └── mock
```

## Quick Overview

Quickly get an idea about each folder's role.

| Directory      | Short Description                                                        |
| :------------- | :----------------------------------------------------------------------- |
| root           | Root directory. Contains many configuration files and all other folders. |
| \_\_tests\_\_  | (Default; as per official template)                                      |
| android        | Android project. Includes modifications to integrate libraries.          |
| e2e            | Detox end-to-end tests and configurations.                               |
| fastlane       | Useful fastlane automation scripts.                                      |
| ios            | iOS project. Includes modifications to integrate libraries.              |
| scripts        | Handy node scripts for code generation.                                  |
| src            | Most of the app's code is here.                                          |
| common         | Shared code between different features.                                  |
| assets         | Shared images, fonts etc.                                                |
| components     | Shared React components.                                                 |
| exceptions     | Shared custom exceptions.                                                |
| helpers        | Shared utlities.                                                         |
| hooks          | Shared hooks.                                                            |
| theme          | Shared styles; app's theme.                                              |
| types          | Shared general types.                                                    |
| features       | Feature directories.                                                     |
| error-boundary | Root error boundary.                                                     |
| home           | Home screen. Has simple data fetching and global state examples.         |
| landing        | Template's initial screen.                                               |
| navigation     | Contains a simple stack navigator.                                       |
| redux          | Redux integration.                                                       |
| middleware     | Redux custom middleware. For now, a simple Sentry breadcrumb logger.     |
| slices         | Redux state slices.                                                      |
| services       | App's services.                                                          |
| cache          | Cache service; AsyncStorage wrapper.                                     |
| navigation     | Navigation service (navigate from outside React components).             |
| network        | Networking related services.                                             |
| github         | Example GitHub API client (REST).                                        |
| mock           | MirageJS in-memory server for mocking backend APIs.                      |

If you would like to learn more without going through the codebase, read the [file walkthrough here](./docs/file-walkthrough.md).

## Credits

*Phantom Design studio*
