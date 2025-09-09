<img width="940" height="119" alt="image" src="https://github.com/user-attachments/assets/d6d46213-7082-421c-8909-3cae64b8b470" /># EX-NO-9-RSA-Algorithm

## AIM:
To Implement RSA Encryption Algorithm in Cryptography

## Algorithm:


Step 1: Design of RSA Algorithm  
The RSA algorithm is based on the mathematical difficulty of factoring the product of two large prime numbers. It involves generating a public and private key pair, where the public key is used for encryption, and the private key is used for decryption.

Step 2: Implementation in Python or C 
This algorithm can be implemented in languages like Python or C by performing large integer calculations for key generation, encryption, and decryption, utilizing libraries for modular arithmetic if necessary.

Step 3: Algorithm Description  
1. Key Generation:
   - Select two large prime numbers \( p \) and \( q \).
   - Calculate \( n = p \times q \), which will be used as the modulus.
   - Compute the totient \( \phi(n) = (p - 1)(q - 1) \).
   - Choose a public exponent \( e \) such that \( e \) is coprime with \( \phi(n) \).
   - Compute the private key \( d \), which is the modular inverse of \( e \) mod \( \phi(n) \).

2. Encryption:
   - Convert the plaintext message \( M \) into a numerical form \( m \) (such that \( 0 \le m < n \)).
   - Compute the ciphertext \( c \) using the formula: \( c = m^e \mod n \).

3. Decryption:
   - Use the private key \( d \) to recover \( m \) from \( c \) using: \( m = c^d \mod n \).
   - Convert \( m \) back into the original message \( M \).

Step 4: Mathematical Representation  
- Encryption: \( E(m) = m^e \mod n \)
- Decryption: \( D(c) = c^d \mod n \)

Step 5: **Security Foundation  
The security of RSA relies on the difficulty of factoring large numbers; thus, choosing sufficiently large prime numbers for \( p \) and \( q \) is crucial for security.

## Program:
```
from Crypto.PublicKey import RSA
from Crypto.Cipher import PKCS1_OAEP
import base64

# Generate RSA keys (2048-bit)
key = RSA.generate(2048)
public_key = key.publickey()
private_key = key

# Take input
plaintext = input("Enter the plaintext: ")

# Encrypt
cipher = PKCS1_OAEP.new(public_key)
encrypted = cipher.encrypt(plaintext.encode())
encrypted_b64 = base64.b64encode(encrypted).decode()
print("\nEncrypted (Base64):", encrypted_b64)

# Decrypt
cipher = PKCS1_OAEP.new(private_key)
decrypted = cipher.decrypt(base64.b64decode(encrypted_b64)).decode()
print("Decrypted:", decrypted)

```



## Output:
<img width="940" height="119" alt="image" src="https://github.com/user-attachments/assets/1fa98713-bc3b-46dc-ae85-f5d0e23d95eb" />



## Result:

Thus, RSA Algorithm has been implemented successfully.
 The program is executed successfully.
