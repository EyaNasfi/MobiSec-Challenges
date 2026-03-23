# AyaNasfi-appdev-unbindable.md

## Description of the problem

The **unbindable** challenge focuses on inter-process communication using Android bound services.
The goal is to bind to a remote service, communicate using 'Messenger', and retrieve the flag sent by the service.

## Solution

I solved this challenge by binding to the target service using an explicit intent.
Once connected, I registered my application as a client and sent a message requesting the flag.

The service responded through the 'Messenger' mechanism, and the flag was received and logged using the 'MOBISEC' tag.
The automated analysis successfully validated the result.

## Optional Feedback

This challenge helps understand how communication works between different applications.
