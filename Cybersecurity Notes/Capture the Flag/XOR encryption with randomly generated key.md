Given the code used to encrypt the flag using XOR and a randomly generated 10 character key, the flag was encrypted 

### Code used to encrypt the flag
```python
#!/usr/bin/env python3

from secret import FLAG

import os



def xor(pt, key):

    ct = []

    for i,c in enumerate(pt):

        ct.append(pt[i]^key[i%len(key)])

    return bytearray(ct)



my_key = os.urandom(10)

ct = xor(FLAG, my_key).hex()

print(f"{ct}")
```

### Process
XOR works by XORing each character of the plaintext with the subsequent character of the key, if the key is shorter than the plaintext, the key get repeated until the whole plaintext is encrypted. XOR also works the other way so the ciphertext can then be XORed with the key to get the plaintext back, or with the plaintext to get the key. < this si what we do to find the first 9 characters of the key since we know the plaintext will start with "flyerCTF{}". We just need to brute force the final 10th character of the key.

### Code used to decrypt the XOR and brute force the final 10th character of the key
```python
import os

def xor(pt, key):
    ct = []
    for i, c in enumerate(pt):
        ct.append(pt[i] ^ key[i % len(key)])
    return bytearray(ct)

# Known prefix
prefix = b"flyerCTF{"

# Given ciphertext
ct = bytes.fromhex("dfbbefc6b2d45f726b86d7e7e1cff3f36c074fdcca88e693b7a4796b2483dd88a7fcabf93b434fd9e6bba6949fe3635d6384caa3fec6a6fb6a537299ceaa")

# Extract first 9 characters of the key
key_prefix = xor(ct[:len(prefix)], prefix)

# Brute force the last character of the key
for i in range(256):  # Try all possible values of the last character
    possible_key = key_prefix + bytes([i])
    decrypted = xor(ct, possible_key)
    if decrypted[:len(prefix)] == prefix:  # Check if decrypted text starts with the known prefix
        print("Found key:", possible_key.hex())
        print("Decrypted:", decrypted)

```