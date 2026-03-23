# AyaNasfi-appdev-whereareyou.md

## Description of the problem

The **whereareyou** challenge is about working with Android location services.
The goal is to receive location requests from another application, provide location updates, and communicate them back correctly.

## Solution

I solved this challenge by implementing a background service that listens for the 'com.mobisec.intent.action.GIMMELOCATION' action.
When the service receives the request, it retrieves the current (or last known) location and broadcasts it back.
The target application receives the location, verifies the coordinates, and returns the flag once the values are correct.
The flag is then printed using the 'MOBISEC' tag.

## Optional Feedback

This challenge helps understand how location services and broadcasts can be combined in Android.
