# AyaNasfi-appdev-justask.md

## Description of the problem

The **justask** challenge is about communicating with another Android application by starting its activities.
Each activity returns a different part of the flag using intents and extras.

## Solution

I solved this challenge by starting the four activities provided by the target application using explicit intents.
For each activity, I handled the result in 'onActivityResult'.
Depending on the part, the flag was hidden in extras or nested bundles.
I inspected the returned intents, extracted the values, and logged them using the 'MOBISEC' tag.

## Optional Feedback

