# Solution

## Description of the problem
This challenge hides a flag behind a 6-digit PIN code.  
Instead of checking the PIN directly, the application applies multiple MD5 hash operations before validating the input.

More precisely, the entered PIN is hashed **25 × 400 times**.  
The final hash is then compared with the following value:

d04988522ddfed3133cc24fb6924eae9

Only a correct PIN will generate this exact hash.

---
## Solution

Since the PIN only contains digits and has a fixed length of 6, the search space is limited to:

000000 → 999999

To solve the challenge, I recreated the hashing process in Java and performed an **offline brute-force attack**:

- Generate every possible 6-digit PIN  
- Apply the same MD5 hashing loops  
- Compare each result with the target hash  
- Stop when a match is found  

---

Result  

After testing all possibilities, the correct PIN was found:

703958

---
## Optional Feedback

