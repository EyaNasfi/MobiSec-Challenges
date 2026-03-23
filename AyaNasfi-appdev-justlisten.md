# AyaNasfi-appdev-justlisten.md

## Description of the problem

The **justlisten** challenge is about listening to what other applications broadcast on the system.  
The goal is to receive a specific broadcast intent, extract the flag from it, and log it correctly.

## Solution

I solved this challenge by creating an application that registers a 'BroadcastReceiver' for the action
'com.mobisec.intent.action.FLAG_ANNOUNCEMENT'.

When the challenge application broadcasts the intent, my receiver catches it, extracts the 'flag'
extra, and prints it in the logs using the 'MOBISEC' tag.  
I also display the received flag on the screen for verification.

After submission, the analysis confirmed that my application correctly received the broadcast and logged
the flag.

## Optional Feedback

This challenge is simple and fun.  
It is a good introduction to broadcast receivers and inter-app communication on Android.
