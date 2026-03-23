# Solution – GoingNative

## Description

The **GoingNative** challenge hides part of its logic inside a native library (`.so` file).  
This means the verification is split into two parts:

- Java code (format checks)
- Native code (real validation)

The goal is to reverse both layers to recover the flag.

---

## Solution

### Java Analysis

After decompiling the APK, I found the `FlagChecker` class.

The function:

- Checks the format `MOBISEC{...}`
- Splits the content using `-`
- Sends both parts to a native function:helloFromTheOtherSide(String s, int i)

- The second part must be **6 digits**

---

### Native Analysis

I reversed the native library using Ghidra.

Inside the function:

- The string must be:native_is_so

- The number must be:31337

If both are correct, the function returns success.

---

## Final Result

MOBISEC{native_is_so-031337}

---

## Conclusion

This challenge shows that:

- Native code can hide logic
- JNI does not make apps secure
- Native binaries can also be reversed






