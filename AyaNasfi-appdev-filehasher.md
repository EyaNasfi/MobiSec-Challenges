# AyaNasfi-appdev-filehasher.md

## Description of the problem

The **filehasher** challenge is about handling files and intents between Android applications.
The goal is to receive a file path through an intent, its SHA-256 hash, and return the result correctly.

## Solution

I solved this challenge by creating an activity that listens for the 'com.mobisec.intent.action.HASHFILE' action.
When the intent is received, the application reads the file from external storage and computes its SHA-256 hash.
The computed hash is then sent back to the calling application using 'setResult'.
The hash is also logged with the 'MOBISEC' tag for verification.

## Optional Feedback

This challenge is simple but interesting.