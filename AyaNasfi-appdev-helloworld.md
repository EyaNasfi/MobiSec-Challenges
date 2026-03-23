# AyaNasfi-appdev-helloworld.md

## Description of the problem

The helloworld challenge is a simple introduction to Android development.  
The goal is to create an application that prints a specific message in the system logs using Android’s Logging API, with the correct tag and log level.

## Solution

I solved this challenge by creating a basic Android application with one activity.  
When the application starts, it prints the required message in the logs using 'Log.i()' with the tag 'MOBISEC'.

I checked the result locally with 'adb logcat' to make sure the message appeared correctly.  
After submission, the platform detected the log and returned the flag.

## Optional Feedback

This challenge is simple and clear. 