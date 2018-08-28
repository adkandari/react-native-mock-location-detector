## React Native Mock Location Detector / Location Spoof Apps Detector

If you are building a location based app in RN, you have to validate if the user is using location spoofing apps or not. This library doesn't let the user use the app if any mock location apps are active on the device

![Image description](https://i.imgur.com/iT7OpSs.gif)


## Getting started

`$ npm install react-native-mock-location-detector --save`

### Mostly automatic installation

`$ react-native link react-native-mock-location-detector`

### Manual installation


#### Android

1. Open up `android/app/src/main/java/[...]/MainActivity.java`
  - Add `import com.mocklocation.reactnative.RNMockLocationDetectorPackage;` to the imports at the top of the file
  - Add `new RNMockLocationDetectorPackage()` to the list returned by the `getPackages()` method
2. Append the following lines to `android/settings.gradle`:
  	```
  	include ':react-native-mock-location-detector'
  	project(':react-native-mock-location-detector').projectDir = new File(rootProject.projectDir, 	'../node_modules/react-native-mock-location-detector/android')
  	```
3. Insert the following lines inside the dependencies block in `android/app/build.gradle`:
  	```
      compile project(':react-native-mock-location-detector')
  	```


## Usage
1. Make sure your app has location permission, before calling this function. 
2. Arguments of function checkMockLocationProvider: Dailogbox Title, Dialogbox Text, Dialogbox Button Text

```javascript
import RNMockLocationDetector from 'react-native-mock-location-detector';

RNMockLocationDetector.checkMockLocationProvider(
    "Mock Location Detected",
    "Please remove any mock location app first to continue using this app.",
    "I Understand"
  ); 
```
  
