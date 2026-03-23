# AyaNasfi-appdev-jokeprovider.md

## Description of the problem

The **jokeprovider** challenge consists in accessing a Content Provider exposed by another Android application.
The objective is to query the provider, retrieve specific entries, and reconstruct the flag from the returned data.

## Solution

I solved this challenge by querying the 'com.mobisec.provider.Joke' Content Provider.
I filtered the data using the author field and concatenated the retrieved joke contents.

Once all parts were collected, the flag was reconstructed and logged using the 'MOBISEC' tag.
The automated analysis successfully detected the flag.

## Optional Feedback

This challenge is fun.
