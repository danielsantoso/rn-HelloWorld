# React Native: How to Setup Your First App

React Native is a framework for building mobile applications with JavaScript and leveraging Reactjs. It uses native UI components. If you are familiar with Reactjs, or come from front end development background, Reactjs uses a virtual DOM which act as a shadow to real DOM available. When an element changes, that change is reflected on the real DOM by Virtual DOM using a node that corresponds to each element. However, in React Native, there is no DOM rather than Native Components which are provided by platforms such iOS and Android. There are no web views here.

React Native has an instance of [JavaScriptCore](https://facebook.github.io/react-native/docs/javascript-environment.html) to execute JS code when an application starts. React Native uses RCTBridgeModule to make a connection between native code and JavaScript code. It is assumed that as you dwell more in development with React Native, you might come across using a thrid party SDK for a specific mobile platform. This bridging will be very helpful.

## Difference between React Native and Reactjs

React Native has its own wrappers around the native components and do not make use of every HTML element. For example, `<View>` which is considered similar to `div` of HTML. This is a major difference between React Native and Reactjs. This also means that you cannot reuse every library that renders HTML and is available for Reactjs. It has its own navigation modules.

## Platform Sepecific Designing

Designing a mobile application for mulitple platforms available with same set of code can be a bit overwhelming. In this case a developer or a development team is left with two choices. Either they come up with a user interface that universal to their application. This means, the UI of the app looks same on every platform. However, this not going to be the case with every application you develop. React Native can detect the platform you are running and conditions can be used to apply the styling.

Diving deeply in the bridging part or platform specific designing part of this article is out of the scope. This is written to familiarize you with basic ecosystem of React Native but I wanted to discuss these topics briefly such that to give an idea of what you are getting into.

## Developer Environment for React Native

These are required depenedencies to setup a local environment and further, to develop any type of application using it, on your machine.

Dependencis required:

* Node.js (using Node.js [installer from the official website](http://nodejs.org/))
* Watchman (used Homebrew for macOS. Windows users can install directly from the source. More information about it [here](https://facebook.github.io/watchman/docs/install.html))

Note: Note that you have a Node.js version `>=4.0` to continue.

To setup Native SDKs for specific platforms:

* iOS (install/have Xcode, it is free and most probably pre installed)
* Android (I'd recommend that you follow instructions [here](https://facebook.github.io/react-native/docs/getting-started.html))

Last step is to install React Native CLI using this command:

```shell
npm install -g react-native-cli
```

The above instructions work best if you need to build native code in your application or want to integrate React Native in an exisiting application. If you want to quickly prototype an application and you can use [Create React Native App](https://facebook.github.io/react-native/docs/getting-started.html) module that is very similar to Create React App. For _Create React Native App_ you are not required to install above dependencies (of course you need Node.js for npm modules) and platform specific SDKs. Facebook itself recommends using [Expo](https://expo.io/) client on your phone to see the app in action. I will be using `react-native-cli` for brevity of the subject of this article.

## Hello World with React Native

To scaffold an app, use the React Native command line interface we just installed in the previous step.

```shell
react-native init HelloWorld

cd HelloWorld
```

If you sneak peak inside the directory to see the structure, you will see a similar one:

![ss-1](https://i.imgur.com/oLF14Nf.png)

Lets try running the app before make any changes. Since I am on mac, I will be suing command:

```shell
react-native run-ios
```

To run the same application in an Android Emulator or device (if connected), you can use the command:

```shell
react-native run-android
```

Since you are running any of the above command for the first time, it takes some minutes for the app show up in an emulator. Do not worry, if everything runs successfully, it will show up.

![ss-2](https://i.imgur.com/j5e0XDX.png)

The code you see above running is available in `App.js`:

![ss-5](https://i.imgur.com/qzoS6nD.png)

If you are familiar with Reactjs, you can easily understand this code. `<View>` stands for wrapper element such as `div` in HTML and `<Text>` stands for `<p>` in HTML.

You will be prompted with a success message and in a new terminal window, Metro Bundler will be running until the application closes.

![ss-3](https://i.imgur.com/AtVV7aG.png)

![ss-4](https://i.imgur.com/aqpnbFC.png)

The file that renders this `App` component is `index.js` in the root directory. You will see this code:

![ss-6](https://i.imgur.com/a1D6caa.png)

Do you notice something? There is no `react-dom` because there is no DOM in React Native. `AppRegistery` is the entery point to run a React Native application. `App` component or any other root component in the app should register by using `AppRegistry.registerComponent` such that a native system can load the bundle of the app and run the app by starting `AppRegistry.runApplication`.

You can read more about `AppRegistery` [here](https://facebook.github.io/react-native/docs/appregistry.html).

Link to the [Github Repo](https://github.com/amandeepmittal/rn-HelloWorld) for this project if you are still curious too see the how the project structure looks rather than trying it out yourself.

🙏 For more questions, contact me on [Twitter](https://twitter.com/amanhimself), or read more about me at my [website](http://amanhimself.me/).
