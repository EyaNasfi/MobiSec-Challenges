# Solution – BabyRev

## Description

The **BabyRev** challenge is an introductory reverse engineering task.  
The application checks a user input using simple rules such as:

- fixed strings  
- character positions  
- case patterns  
- basic transformations (ROT13)

The goal is to understand these rules and rebuild the correct flag.

---

## Analysis

After decompiling the APK, I analyzed the `FlagChecker` class.

I found that:

- The flag must start with `MOBISEC{`
- The inner part has a fixed length
- It starts with `this_is_`
- It ends with `sic_rev` (reverse of `ver_cis`)
- A part of the flag is encoded with **ROT13**
- Some characters depend on others
- A regex forces alternating upper/lower case letters

---

## Solution

To solve it, I wrote a small Java script that:

- Builds the flag step by step  
- Applies all constraints  
- Tests each candidate using the original logic  

After reconstruction, the correct flag was found.

---

## Final Result
MOBISEC{ThIs_iS_A_ReAlLy_bAsIc_rEv}

---

## Conclusion

This challenge shows that:

- Even simple checks can hide the flag  
- Static analysis is often enough  
- Understanding conditions is more important than brute force  
