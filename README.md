[![NPM version](http://img.shields.io/npm/v/appium-android-driver.svg)](https://npmjs.org/package/appium-android-driver)
[![Downloads](http://img.shields.io/npm/dm/appium-android-driver.svg)](https://npmjs.org/package/appium-android-driver)
[![Dependency Status](https://david-dm.org/appium/appium-android-driver.svg)](https://david-dm.org/appium/appium-android-driver)
[![devDependency Status](https://david-dm.org/appium/appium-android-driver/dev-status.svg)](https://david-dm.org/appium/appium-android-driver#info=devDependencies)

[![Build Status](https://travis-ci.org/appium/appium-android-driver.svg?branch=master)](https://travis-ci.org/appium/appium-android-driver)
[![Coverage Status](https://coveralls.io/repos/appium/appium-android-driver/badge.svg?branch=master)](https://coveralls.io/r/appium/appium-android-driver?branch=master)

# Appium Android Driver

Appium Android Driver is a test automation tool for Android devices. Appium Android Driver automates native, hybrid and mobile web apps, tested on simulators, emulators and real devices. Appium Android Driver is part of the [Appium](https://github.com/appium/appium) mobile test automation tool.

*Note*: Issue tracking for this repo has been disabled. Please use the [main Appium issue tracker](https://github.com/appium/appium/issues) instead.

## Installation
```
npm install appium-android-driver
```

## Usage
Import Android Driver, set [desired capabilities](http://appium.io/slate/en/1.5/?javascript#appium-server-capabilities) and create a session:

```
import { AndroidDriver } from `appium-android-driver`

let defaultCaps = {
  app: 'path/to/your.apk',
  deviceName: 'Android',
  platformName: 'Android'
};

let driver = new AndroidDriver();
await driver.createSession(defaultCaps);
```
Run commands:
```
await driver.setOrientation('LANDSCAPE');
console.log(await driver.getOrientation()); // -> 'LANDSCAPE'
```

### Specifying and selecting devices/emulators
The driver will attempt to connect to a device/emulator based on these properties in the `desiredCapabilities` object:

1. `avd`: Launch or connect to the emulator with the given name.
1. `udid`: Connect to the device with the given UDID.
1. `platformVersion`: Connect to the first device or active emulator whose OS begins with the desired OS. This means `platformVersion: 5` will take the first `5x` device from the output of `adb devices` if there are multiple available.

If none of these capabilities are given, the driver will connect to the first device or active emulator returned from the output of `adb devices`.

If more than one of these capabilities are given, the driver will only use first the capability in the order above. That is, `avd` takes priority over `udid`, which takes priority over `platformVersion`.

## Commands
|          Command           |
|----------------------------|
| `activateIMEEngine`        |
| `availableIMEEngines`      |
| `back`                     |
| `background`               |
| `clear`                    |
| `click`                    |
| `complexTap`               |
| `deactivateIMEEngine`      |
| `defaultContextName`       |
| `defaultWebviewName`       |
| `doKey`                    |
| `doTouchAction`            |
| `doTouchDrag`              |
| `drag`                     |
| `elementDisplayed`         |
| `elementEnabled`           |
| `elementSelected`          |
| `fakeFlick`                |
| `fakeFlickElement`         |
| `findElOrEls`              |
| `fixRelease`               |
| `flick`                    |
| `getActiveIMEEngine`       |
| `getAlertText`             |
| `getAttribute`             |
| `getContexts`              |
| `getCurrentActivity`       |
| `getCurrentContext`        |
| `getDeviceTime`            |
| `getDisplayDensity`        |
| `getLocationInView`        |
| `getLog`                   |
| `getLogTypes`              |
| `getName`                  |
| `getNetworkConnection`     |
| `getOrientation`           |
| `getPageSource`            |
| `getScreenshot`            |
| `getSize`                  |
| `getStrings`               |
| `getSystemBars`            |
| `getText`                  |
| `getWindowSize`            |
| `hideKeyboard`             |
| `installApp`               |
| `isAppInstalled`           |
| `isIMEActivated`           |
| `isKeyboardShown`          |
| `isLocked`                 |
| `isWebContext`             |
| `keyevent`                 |
| `keys`                     |
| `lock`                     |
| `longPressKeyCode`         |
| `onChromedriverStop`       |
| `openNotifications`        |
| `openSettingsActivity`     |
| `parseTouch`               |
| `performGesture`           |
| `performMultiAction`       |
| `performTouch`             |
| `pinchClose`               |
| `pinchOpen`                |
| `postAcceptAlert`          |
| `postDismissAlert`         |
| `pressKeyCode`             |
| `pullFile`                 |
| `pullFolder`               |
| `pushFile`                 |
| `removeApp`                |
| `replaceValue`             |
| `reset`                    |
| `setAlertText`             |
| `setContext`               |
| `setGeoLocation`           |
| `setLocation`              |
| `setNetworkConnection`     |
| `setOrientation`           |
| `setValue`                 |
| `setUrl`                   |
| `startActivity`            |
| `startChromedriverProxy`   |
| `stopChromedriverProxies`  |
| `suspendChromedriverProxy` |
| `swipe`                    |
| `tap`                      |
| `toggleData`               |
| `toggleFlightMode`         |
| `toggleLocationServices`   |
| `toggleSetting`            |
| `toggleWiFi`               |
| `touchDown`                |
| `touchLongClick`           |
| `touchMove`                |
| `touchUp`                  |
| `unlock`                   |
| `wrapBootstrapDisconnect`  |


## API Notes

`lock` behaves differently in Android than it does in iOS. In Android it does not take any arguments, and locks the screen and returns immediately.


## Watch

```
npm run watch
```

## Test

```
npm test
```
