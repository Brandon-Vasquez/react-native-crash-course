<p align="center"><Img src="https://github.com/wix-playground/react-native-crash-course/blob/master/assets/banner.png" allign="center"></p>

# React Native Crash Course by Wix

The React Native crash course by Wix is a self-learning course designed to help you learn everything
you need to know before diving into writing production code in [React Native](https://facebook.github.io/react-native/).
This course is part of the official onboarding plan for every new developer joining the Wix Mobile Guild.

The course is divided into 2 sections:

## 1. Learn the basics

Helps you untangle the environment setup, learn basics or refresh your knowledge of JS, React, Node, Git, etc. If you already feel comfortable with these subjects, you can jump straight into the next section.

- [Environment setup](/docs/Basics.enviromentSetup.md)
- [Intro to Git & GitHub](/docs/Basics.IntroToGit.md)
- [JS](/docs/Basics.JavaScript.md)
- [React Native](/docs/Basics.ReactNative.md)

## 2. Build your first app

This step-by-step guide will teach you about the best practices and open source tools we are using at Wix and will guide you through building a simple blog app.

1. [Intro](/docs/App.Intro.md)
2. [Build the **app navigation**](/docs/App.Navigation.md) (with React-native-navigation)
3. [Adding the **app business logic** and **state management**](/docs/App.Remx.md) (with Remx)
4. [**Style** the app](/docs/App.UiLib.md) (with react-native-ui-lib)
5. [Add **e2e tests**](/docs/App.e2e.md) (with Detox)
6. [Add **unit tests**](/docs/App.tests.md) (with Jest)
7. [Adding a **Native Module**](/docs/App.NativeModule.md)
8. [Performance - Tools and Best Practice](/docs/App.performance.md)

Here is how our app will look like:

![The app that we are going to build](https://github.com/wix-playground/wix-mobile-crash-course/blob/master/assets/finalApp.gif)

Let's start. 🚀

> Note: The most important thing about any course, is to keep it up to date. We encourage the old Scout's rule: "Leave the campground cleaner than you found it". If you find any issues or out of date content, please send us a pull request or open an issue we will take care of it. Thanks!

We are always working on improving the course content and we would love to get your [feedback](https://docs.google.com/forms/d/e/1FAIpQLSfceLeyvKe2jkk0dkT6LdVE9CA5uq3J-Jt3sCkEhs07hQRVZQ/viewform?usp=sf_link).

## How To Run the App

```
npm install
npm run fake-server
react-native run-ios / run-android
```

- prerequisites:
  - npm `json-server` package
  - ios simulator - Hardware -> Keyboard -> Toggle Software Keyboard

## How To Run the Tests

```
npm run start-e2e
npm run test
```

## Redux

Redux is a state
management tool. This means that it helps you manage the data you display and how your
program responds to user actions. Okay … what is a state then? What is an action?

Upon my research and understanding of Redux, I came across many different vocabulary words
that I did not fully understand how they related to Redux and why they were so important in
redux. Words like store, state, action, reducers, dispatch, pure and impure functions were the
ones that I came across frequently when researching Redux.

A store holds the state and gives access to many useful functions.

A state is the data that represents a part of the app that can change. I hacked on a very basic
example using redux where I created a number counter and the user can increment or decrement
the number that is displayed. If you press the “+” button on the app, the number that is shown
increases by a certain value, in my example the number increases by 5. With all that being said,
the number (integer) represents the state.

An action is just a plain javascript object and it usually has a payload and always has a type as its
properties. In my redux-counter example, the “actions” are the incrementing and decrementing of
the number.

A reducer is the pure function (will explain pure function below) that knows what to do with an
action and its information (payload). The current state and action are passed in the function and it
returns a new state. In my example, the reducer function basically the action passed in as an
argument and allows the number to be incremented and/or decremented which returns a new
number.

Pure and impure functions: a pure function would always return the same result every time it is
called, whereas in an impure function the result would always be different.

Dispatch is a function that updates the application state and it is the only way to update the
application state. In my example, the dispatch is called in the button JSX tag and the increment
and decrement functions are passed in. So, every time the user clicks the “+” or “-“ buttons, it
triggers the change/update of the number (state).

Knowing all of these terms and their purpose in Redux made it easier to understand the
Principles of Redux which are: Single Source of Truth, State is Read Only, and Views cannot change the state Directly. “Single source of truth” means that the state of your whole app is
stored in an object tree within one store, so it makes the code easier to look at and debugging is
easier as well. “State is read only” means, as mentioned before, that the only way to change the
state is to dispatch an action. “Views cannot change the state directly” which basically reinforces
the idea that in Redux you dispatch actions, and actions tell the reducer to update the state, and
each action instructs the reducers to replace the existing state with a new version.
