# EX-NO-7-Implement-DES-Encryption

## Aim:

To use the Data Encryption Standard (DES) algorithm for a practical application, such as securing sensitive data transmission in financial transactions.

## ALGORITHM:

1. DES is based on a symmetric key encryption technique that encrypts data in 64-bit blocks.
2. DES uses a Feistel network structure with 16 rounds of processing for encryption.
3. DES has a 64-bit key, but only 56 bits are used for encryption (the remaining 8 bits are for parity).
4. DES applies initial and final permutations along with 16 rounds of substitution and permutation transformations to produce ciphertext.

## Program:
```
from pyDes import des, PAD_PKCS5
import binascii
def des_encrypt(data, key):
    cipher = des(key, padmode=PAD_PKCS5)
    encrypted_data = cipher.encrypt(data)
    return binascii.hexlify(encrypted_data).decode()
def des_decrypt(encrypted_data, key):
    cipher = des(key, padmode=PAD_PKCS5)
    decrypted_data = cipher.decrypt(binascii.unhexlify(encrypted_data))
    return decrypted_data.decode()
if __name__ == "__main__":
    text = input("Enter text to encrypt: ")
    key = input("Enter 8-character key: ")
    if len(key) != 8:
        print("Error: Key must be exactly 8 characters long!")
    else:
        encrypted = des_encrypt(text, key)
        print("\nEncrypted Text (in hex):", encrypted)

        decrypted = des_decrypt(encrypted, key)
        print("Decrypted Text:", decrypted)
```
## Output:

<img width="586" height="129" alt="image" src="https://github.com/user-attachments/assets/0cb1ba2c-d603-4d08-accd-19d076f6fb8b" />

## Result:
  The program is executed successfully.
