#  Push Notification Testing

## Overview
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

## Example 1
$ xcrun simctl push booted com.jeenalinfotech.TestPushNotificationOnSimulator Payload.json
Notification sent to 'com.jeenalinfotech.TestPushNotificationOnSimulator'

## Example 2
$ xcrun simctl push <DeviceID> <Bundle-Identifier> Payload.json

// You can get the all the Device IDs using following command:
$ xcrun simctl list devices

// Use following command to get to Booted Device IDs
$ xcrun simctl list devices | grep Booted

Output:
iPhone SE (2nd generation) (CA5DDEF2-56B6-477F-A7A6-68569E11BEFB) (Booted) 
