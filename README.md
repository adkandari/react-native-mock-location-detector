Hi, I am sorry I am not maintaining this library from quite sometime now. You can check a new fork of this one https://github.com/jpudysz/react-native-turbo-mock-location-detector, looks like it is maintained regularly. Thanks to https://github.com/jpudysz

## React Native Mock Location Detector / Location Spoof Apps Detector

⚠️ A fork of [react-native-mock-location-detector](https://github.com/adkandari/react-native-mock-location-detector) but with fixes.

If you are building a location based app in RN, you have to validate if the user is using location spoofing apps or not. This library doesn't let the user use the app if any mock location apps are active on the device

![Image description](https://i.imgur.com/iT7OpSs.gif)

## Getting started

`$ npm install react-native-detect-mock-location --save`

### Mostly automatic installation

`$ react-native link react-native-detect-mock-location`

### Manual installation

#### Android

1. Open up `android/app/src/main/java/[...]/MainActivity.java`

- Add `import com.mocklocation.reactnative.RNMockLocationDetectorPackage;` to the imports at the top of the file

- Add `new RNMockLocationDetectorPackage()` to the list returned by the `getPackages()` method

2. Append the following lines to `android/settings.gradle`:

```

include ':react-native-mock-location-detector'

project(':react-native-mock-location-detector').projectDir = new File(rootProject.projectDir, '../node_modules/react-native-mock-location-detector/android')

```

3. Insert the following lines inside the dependencies block in `android/app/build.gradle`:

```

implementation project(':react-native-mock-location-detector')

```

## Usage

1. Make sure your app has location permission, before calling this function.

2. Arguments of function checkMockLocationProvider: Dailogbox Title, Dialogbox Text, Dialogbox Button Text

```javascript
import RNMockLocationDetector from "react-native-detect-mock-location";

const isLocationMocked: boolean =
  await RNMockLocationDetector.checkMockLocationProvider();

if (isLocationMocked) {
  // Location is mocked or spoofed

  return;
}

// Location is fine
```
