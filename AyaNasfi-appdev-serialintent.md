# AyaNasfi-appdev-serialintent.md

## Description of the problem

The **serialintent** challenge is about passing complex objects between applications using intents.
The goal is to receive a serialized object, understand its structure, and reconstruct the hidden flag.

## Solution

I solved this challenge by starting the target activity and receiving the returned intent.
The flag was embedded inside a serialized object ('FlagContainer') containing shuffled Base64 fragments.

By using the target application's class loader, I was able to deserialize the object correctly and invoke its internal method to reconstruct the flag.
Once recovered, the flag was logged using the 'MOBISEC' tag.

## Optional Feedback

This challenge is interesting and it is a good exercise to understand serialization, class loaders, and intent-based object passing in Android.
