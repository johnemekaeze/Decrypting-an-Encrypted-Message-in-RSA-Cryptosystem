# Decrypting an RSA-Encrypted Message

This project implements the entire RSA decryption process along with custom message decoding.

## Overview

In this exercise, we work with an RSA-encrypted message. The public key is given as \((e, n)\) and the ciphertext is composed of several large numeric values. The original plaintext was encoded using a custom two-digit mapping scheme:
- `"00"` maps to a space,
- `"11"` through `"36"` map to the letters A–Z.

## What This Project Does

1. **RSA Key Recovery:**  
   The RSA modulus \( n \) is factorized into its two prime factors \( p \) and \( q \) using Sympy’s `factorint`. Euler's totient function is then computed as \(\phi(n) = (p-1)(q-1)\), and the Extended Euclidean Algorithm is used to calculate the modular inverse of \( e \) modulo \(\phi(n)\) to obtain the private key \( d \).

2. **Decryption:**  
   The ciphertext values are decrypted using the RSA decryption formula \( m = c^d \mod n \). The result is a numeric message that remains encoded.

3. **Decoding:**  
   The decrypted numeric message is converted to a string and split into two-digit groups. Each group is mapped to its corresponding character using the custom mapping. The final decoded message is:

**THIS IS MY LETTER TO THE WORLD THAT NEVER WROTE TO ME EMILY DICKINSON**
