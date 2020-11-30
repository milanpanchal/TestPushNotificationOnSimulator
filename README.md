#  Push Notification Testing
* With the release of Xcode 11.4, developer does not require real device to test push notificaion. Now, they can directly test push notification using iOS Simulator.

* Using `simctl` commnad you can send the push notification to your iOS simulator.

## Overview
```shell
$ xcrun simctl push --help

Send a simulated push notification
Usage: simctl push <device> [<bundle identifier>] (<json file> | -)

	bundle identifier
	     The bundle identifier of the target application
	     If the payload file contains a 'Simulator Target Bundle' top-level key this parameter may be omitted.
	     If both are provided this argument will override the value from the payload.
	json file
	     Path to a JSON payload or '-' to read from stdin. The payload must:
	       - Contain an object at the top level.
	       - Contain an 'aps' key with valid Apple Push Notification values.
	       - Be 4096 bytes or less.

Only application remote push notifications are supported. VoIP, Complication, File Provider, and other types are not supported.
```



## Example 1

```shell
$ xcrun simctl push booted com.jeenalinfotech.TestPushNotificationOnSimulator Payload.json
Notification sent to 'com.jeenalinfotech.TestPushNotificationOnSimulator'
```



## Example 2

```shell
$ xcrun simctl push <DeviceID> <Bundle-Identifier> Payload.json

// You can get the all the Device IDs using following command:
$ xcrun simctl list devices

// Use following command to get to Booted Device IDs
$ xcrun simctl list devices | grep Booted
iPhone SE (2nd generation) (CA5DDEF2-56B6-477F-A7A6-68569E11BEFB) (Booted)
```



## Author

**Milan Panchal**, follow me on:

1. **Twitter** ([@milan_panchal24](https://twitter.com/milan_panchal24))
2. **Github** ([/milanpanchal](https://github.com/milanpanchal/))
3. **Medium** ([https://medium.com/@milanpanchal24](https://medium.com/@milanpanchal24))
4. **LinkedIn** ([/in/milanpanchal/](https://www.linkedin.com/in/milanpanchal/))
5. **LeedCode** ([/milanpanchal](https://leetcode.com/milanpanchal/))



License
----

MIT

**Free Software, Hell Yeah!**