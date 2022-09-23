<h1 align="center">

<p align="center">
  <img src="./assets/hero.png"/>
</p>

<p align="center">
  <a href="https://www.npmjs.com/package/react-native-voice-recorder"><img src="http://img.shields.io/npm/v/react-native-voice-recorder.svg?style=flat" /></a>
  <a href="https://github.com/prscX/react-native-voice-recorder/pulls"><img alt="PRs Welcome" src="https://img.shields.io/badge/PRs-welcome-brightgreen.svg" /></a>
  <a href="https://github.com/prscX/react-native-voice-recorder#License"><img src="https://img.shields.io/npm/l/react-native-voice-recorder.svg?style=flat" /></a>
</p>


    ReactNative: Native Voice Recorder (Android/iOS)
This version is fixed for latest versions of Android by @gabrielalao.

If this project has helped you out, please support us with a star 🌟
</h1>
This library is a React Native bridge around native voice recorder libraries. It allows you to record and play voice.


#### iOS

| **[hackiftekhar/IQAudioRecorderController](https://github.com/hackiftekhar/IQAudioRecorderController)**             |
| ----------------- |
| <img src="./assets/ios.gif" />                  |


#### Android

| **[adrielcafe/AndroidAudioRecorder](https://github.com/adrielcafe/AndroidAudioRecorder)**             |
| ----------------- |
| <img src="https://raw.githubusercontent.com/adrielcafe/AndroidAudioRecorder/master/demo.gif" />                  |


## 📖 Getting started

`$ yarn add react-native-voice-recorder`

## **RN60 >= RNVR V1 >**

> RN60 above please use `react-native-voice-recorder` V1 and above

- **iOS**

> **iOS Prerequisite:** Please make sure `CocoaPods` is installed on your system

	- Add the following to your `Podfile` -> `ios/Podfile` and run pod update:


```
  pod 'IQAudioRecorderController', :git => 'https://github.com/prscX/IQAudioRecorderController', :branch => 'wav'

  use_native_modules!

  pod 'RNVoiceRecorder', :path => '../node_modules/react-native-voice-recorder/ios'
```

- **Android**

  * Please add below user permission to your app `AndroidManifest`:

```
    <uses-permission android:name="android.permission.RECORD_AUDIO"/>
    <uses-permission android:name="android.permission.READ_EXTERNAL_STORAGE" />
    <uses-permission android:name="android.permission.WRITE_EXTERNAL_STORAGE" />
    <uses-permission android:name="android.permission.WAKE_LOCK" />
```


## **RN60 < RNVR V1 <**

> RN60 below please use `react-native-voice-recorder` V.0.*


`$ react-native link react-native-voice-recorder`


* Android
  * Please add below script in your build.gradle

```
buildscript {
    repositories {
        jcenter()
        maven { url "https://maven.google.com" }
        maven { url "https://jitpack.io" }
        ...
    }
}

allprojects {
    repositories {
        mavenLocal()
        jcenter()
        maven { url "https://maven.google.com" }
        maven { url "https://jitpack.io" }
        ...
    }
}
```

  * Please add below user permission to your app `AndroidManifest`:

```
    <uses-permission android:name="android.permission.RECORD_AUDIO"/>
    <uses-permission android:name="android.permission.READ_EXTERNAL_STORAGE" />
    <uses-permission android:name="android.permission.WRITE_EXTERNAL_STORAGE" />
    <uses-permission android:name="android.permission.WAKE_LOCK" />
```

> **Note:** Android SDK 27 > is supported

* iOS
    > **iOS Prerequisite:** Please make sure CocoaPods is installed on your system

  * After `react-native link react-native-voice-recorder`, please verify `node_modules/react-native-voice-recorder/ios/` contains `Pods` folder. If does not exist please execute `pod install` command on `node_modules/react-native-voice-recorder/ios/`, if any error => try `pod repo update` then `pod install`
  * After verification, open your project and create a folder 'RNVoiceRecorder' under Libraries.
  * Drag `node_modules/react-native-voice-recorder/ios/pods/Pods.xcodeproject` into RNVoiceRecorder, as well as the RNVoiceRecorder.xcodeproject if it does not exist.
  * Add the `IQAudioRecorderController.framework` & `SCSiriWaveformView.framework` into your project's `Embedded Binaries` and make sure the framework is also in linked libraries.
  * Go to your project's `Build Settings -> Frameworks Search Path` and add `${BUILT_PRODUCTS_DIR}/IQAudioRecorderController` & `${BUILT_PRODUCTS_DIR}/SCSiriWaveformView` non-recursive.

  * Now build your iOS app through Xcode

## 💻 Usage

```javascript
import { RNVoiceRecorder } from 'react-native-voice-recorder';

RNVoiceRecorder.Record({
    onDone: (path) => {

    },
    onCancel: () => {

    }
})

RNVoiceRecorder.Play({
    path: '',
    onDone: (path) => {

    },
    onCancel: () => {

    }
})

```


## 💡 Props

- **General(iOS & Android)**

| Prop                   | Type                | Default | Note                                             |
| ---------------------- | ------------------- | ------- | ------------------------------------------------ |
| `path: mandatory`     | `string`            |         | Specify media path to play                 |
| `onDone`    | `func` |         | Specify done callback            |
| `onCancel`        | `func`            |      | Specify cancel callback       |


## ✨ Credits

- [hackiftekhar/IQAudioRecorderController](https://github.com/hackiftekhar/IQAudioRecorderController)
- [adrielcafe/AndroidAudioRecorder](https://github.com/adrielcafe/AndroidAudioRecorder)

## 🤔 How to contribute
Have an idea? Found a bug? Please raise to [ISSUES](https://github.com/prscX/react-native-voice-recorder/issues).
Contributions are welcome and are greatly appreciated! Every little bit helps, and credit will always be given.

## 💫 Where is this library used?
If you are using this library in one of your projects, add it in this list below. ✨


## 📜 License
This library is provided under the Apache 2 License.

