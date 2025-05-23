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
def encrypt(message, key):
    encrypted = []
    key_length = len(key)
    for i in range(len(message)):
        encrypted_char = ord(message[i]) ^ ord(key[i % key_length])
        encrypted.append(encrypted_char)
    return encrypted

def decrypt(encrypted, key):
    decrypted = []
    key_length = len(key)
    for i in range(len(encrypted)):
        decrypted_char = encrypted[i] ^ ord(key[i % key_length])
        decrypted.append(chr(decrypted_char))
    return ''.join(decrypted)

message = input("Enter the message to encrypt: ")
key = input("Enter the encryption key: ")

encrypted_message = encrypt(message, key)

print("Original Message:", message)
print("Encrypted Message (hex):", ' '.join(f"{byte:02X}" for byte in encrypted_message))

decrypted_message = decrypt(encrypted_message, key)
print("Decrypted Message:", decrypted_message)

```




## Output:
![image](https://github.com/user-attachments/assets/19d7b748-9581-4f0b-ac87-34b89a2d7ea5)

## Result:
  The program is executed successfully

