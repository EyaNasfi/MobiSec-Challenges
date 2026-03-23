# Solution – Gnirts

## Description

The **Gnirts** challenge checks a flag using several obfuscation techniques:
Base64 decoding, XOR strings and cryptographic hashes.

The goal is to understand how the app verifies the input and rebuild the correct flag.

---

## Analysis

The flag format is:

MOBISEC{ps0-ps1-ps2-ps3-ps4}

After reversing the code, I found that:
- The separator is `-`
- The flag is split into 5 parts
- Each part has its own rules (length and characters)
- Each part is checked using **MD5**
- The full flag is verified again with **SHA-256**

---

## Solution

I solved the challenge by:

- Extracting the target hashes
- Brute-forcing each part separately
- Following the character rules
- Stopping when the hash matched

Recovered parts:

ps0 → peppa  
ps1 → 9876543  
ps2 → BAAAM  
ps3 → A1z9  
ps4 → 3133337  

---

## Final Flag

MOBISEC{peppa-9876543-BAAAM-A1z9-3133337}

---

## Conclusion

This challenge shows that:
- Obfuscation can be reversed
- Hash checks can be brute-forced
- Client-side protection is not secure
