# Solution – Blockchain

## Description

The **Blockchain** challenge uses multiple layers of AES encryption.  
Instead of encrypting once, the data is encrypted **10 times in a row** using keys derived from a small seed.

The key is only **3 bytes long**, which means there are:

2^24 = 16,777,216 possible keys

Each key is transformed several times using MD5 before being used for AES.

---

## Analysis

The encryption process works like this:

1. Start with a 3-byte key  
2. Compute:
   - key0 = MD5(seed)
   - key1 = MD5(key0)
   - ...
   - key9 = MD5(key8)
3. The ciphertext must be decrypted in reverse order:
   - key9 → key8 → ... → key0
4. After all decryptions, the plaintext appears

---

## Solution

Instead of testing keys on the phone, I created a **Java brute-force tool**.

What the tool does:

- Tries all possible 3-byte keys  
- Generates the 10 MD5 keys  
- Decrypts the ciphertext 10 times  
- Checks if the result looks like a flag  
- Stops when `MOBISEC{...}` is found  

The program uses **multi-threading** to be faster.

---

## Result

Key found:ae098e

Recovered flag:
MOBISEC{blockchain_failed_to_deliver_once_again}

---

## Conclusion

This challenge shows that:
- Using small keys is insecure  
- Repeated encryption does not fix weak key size  
- Offline brute-force is very effective  
