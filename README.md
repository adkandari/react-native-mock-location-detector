
# react-native-mock-location-detector

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
```javascript
import RNMockLocationDetector from 'react-native-mock-location-detector';

// TODO: What to do with the module?
RNMockLocationDetector;
```
  