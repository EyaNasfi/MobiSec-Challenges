# Solution – LoadMe

## Problem Description

The **LoadMe** challenge focuses on dynamic code loading.  
The main APK does not directly contain the flag verification logic.  
Instead, it decrypts and loads multiple hidden stages at runtime using `DexClassLoader`.

Each stage reveals another encrypted file, forcing us to go deeper step by step.

---

## Analysis

The application uses **three XOR decryption layers**.

### Stage 1

- File: `stage1.enc` (inside assets)
- XOR key: `com.mobisec.dexclassloader`
- Output: `stage1.apk`

### Stage 2

- File: `logo.png` (inside stage1 assets)
- XOR key: `weneedtogodeeper`
- Output: `logo.dex`

### Stage 3

- The decrypted `logo.dex` contains the final verification logic.

---

## Solution

To solve the challenge, I followed these steps:

1. Extracted `stage1.enc` from the original APK  
2. Wrote a script to XOR-decrypt it using the package name  
3. Decompiled `stage1.apk` with JADX  
4. Extracted `logo.png` from its assets  
5. XOR-decrypted it using the second key  
6. Decompiled `logo.dex`  
7. Read the flag directly from the Java code

---

## Final Result

MOBISEC{dynamic_code_loading_can_make_everything_tricky_eh?}
---

## Conclusion

This challenge shows that:

- Hiding logic in multiple layers does not guarantee security
- Dynamic code loading can always be reversed
- Encryption keys stored in the app offer no real protection
