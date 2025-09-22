# EX-NO-7-Implement-DES-Encryption

## Aim:

To use the Data Encryption Standard (DES) algorithm for a practical application, such as securing sensitive data transmission in financial transactions.

## ALGORITHM:

1. DES is based on a symmetric key encryption technique that encrypts data in 64-bit blocks.
2. DES uses a Feistel network structure with 16 rounds of processing for encryption.
3. DES has a 64-bit key, but only 56 bits are used for encryption (the remaining 8 bits are for parity).
4. DES applies initial and final permutations along with 16 rounds of substitution and permutation transformations to produce ciphertext.

## Program:
~~~
def encrypt(message, key):
    encrypted = []
    key_length = len(key)
    for i in range(len(message)):
        encrypted.append(chr(ord(message[i]) ^ ord(key[i % key_length])))
    return "".join(encrypted)

def decrypt(encrypted_message, key):
    decrypted = []
    key_length = len(key)
    for i in range(len(encrypted_message)):
        decrypted.append(chr(ord(encrypted_message[i]) ^ ord(key[i % key_length])))
    return "".join(decrypted)


def main():
    message = "Sharveshwaran SS"   # fixed name
    print("\n**Simulation of DES-like XOR encryption and decryption**\n")
    print(f"Original Message: {message}")

    key = input("Enter the encryption key: ")

    encrypted_message = encrypt(message, key)
    print("Encrypted Message (hex):", " ".join(f"{ord(c):02X}" for c in encrypted_message))

    decrypted_message = decrypt(encrypted_message, key)
    print("Decrypted Message:", decrypted_message)


if __name__ == "__main__":
    main()

~~~
## Output:
<img width="1870" height="1075" alt="Screenshot 2025-09-22 134926" src="https://github.com/user-attachments/assets/424aafbd-67ee-4e28-b847-678155ba0978" />

## Result:
  The program is executed successfully

