# Solution – UPOS

## Problem Description

The **UPOS** challenge is an Android application designed to block both:

- Dynamic analysis (debuggers, Frida)
- Static modifications (APK tampering)

The app checks a user-provided flag using a heavily obfuscated algorithm based on:

- A custom pseudo-random number generator (PRNG)
- External data stored in a file called `lotto.dat`

Several security checks are implemented:

- Debugger detection  
- Frida detection  
- Google Play presence check  
- APK signature verification  

If any of these checks fail, the app immediately stops.  
This means debugging directly on the app is not practical.

---

## Analysis

### Flag Verification Logic

The flag is verified inside:

`FC.checkFlag(Context ctx, String flag)`

The method:

- Reads numeric values from `lotto.dat`
- Uses a custom **LFSR-based PRNG**
- Processes the flag **two characters at a time**
- Compares computed values with internal targets

---

## Offline Reimplementation

To bypass the protections, I reimplemented the verification logic **outside Android**:

- Extracted `lotto.dat`
- Recreated the PRNG behavior
- Simulated the flag validation algorithm in Java

I created small tools to:

- Find correct PRNG parameters  
- Identify valid character pairs  
- Rebuild the final flag  

---

## Solution Steps

1. Extracted `lotto.dat` from the APK  
2. Reversed the PRNG configuration  
3. Enumerated valid character pairs  
4. Reconstructed the full flag from pairs  

One tricky part was the sequence: sh^W_

The `^W` is a backspace character used as an obfuscation trick.

---

## Final Result

MOBISEC{Isnt_this_a_truly_evil_undebuggable_piece_of_sh^W_software??}

---

## Conclusion

This challenge demonstrates:

- Why anti-debug protections are not enough
- How offline reversing bypasses runtime defenses
- The danger of relying only on client-side security
