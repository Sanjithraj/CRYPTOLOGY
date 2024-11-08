import random

# Step 1: Choose two prime numbers p and q
p = 61
q = 53
n = p * q
phi = (p - 1) * (q - 1)

# Step 2: Choose an integer e such that 1 < e < phi(n) and gcd(e, phi(n)) = 1
e = 17  # Commonly used value of e

# Step 3: Calculate d such that (d * e) % phi = 1
d = pow(e, -1, phi)  # Python's built-in function for modular inverse

# Function to encrypt a message
def encrypt(message, e, n):
    return [pow(ord(char), e, n) for char in message]

# Function to decrypt a message
def decrypt(ciphertext, d, n):
    return ''.join([chr(pow(char, d, n)) for char in ciphertext])

# Testing the encryption and decryption
message = "HELLO"
ciphertext = encrypt(message, e, n)
print("Ciphertext:", ciphertext)

decrypted_message = decrypt(ciphertext, d, n)
print("Decrypted Message:", decrypted_message)
