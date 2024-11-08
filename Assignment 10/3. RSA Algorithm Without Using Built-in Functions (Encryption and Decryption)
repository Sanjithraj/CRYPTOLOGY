# Helper function to calculate gcd
def gcd(a, b):
    while b != 0:
        a, b = b, a % b
    return a

# Helper function to calculate modular exponentiation
def modular_exponentiation(base, exp, mod):
    result = 1
    base = base % mod
    while exp > 0:
        if (exp % 2) == 1:
            result = (result * base) % mod
        exp = exp >> 1
        base = (base * base) % mod
    return result

# Helper function to calculate modular inverse using Extended Euclidean Algorithm
def modular_inverse(e, phi):
    t, newt = 0, 1
    r, newr = phi, e
    while newr != 0:
        quotient = r // newr
        t, newt = newt, t - quotient * newt
        r, newr = newr, r - quotient * newr
    if t < 0:
        t = t + phi
    return t

# RSA Key Generation
p = 61
q = 53
n = p * q
phi = (p - 1) * (q - 1)

e = 17
while gcd(e, phi) != 1:
    e += 1

d = modular_inverse(e, phi)

# Encryption function
def encrypt(message, e, n):
    return [modular_exponentiation(ord(char), e, n) for char in message]

# Decryption function
def decrypt(ciphertext, d, n):
    return ''.join([chr(modular_exponentiation(char, d, n)) for char in ciphertext])

# Testing the encryption and decryption
message = "HELLO"
ciphertext = encrypt(message, e, n)
print("Ciphertext:", ciphertext)

decrypted_message = decrypt(ciphertext, d, n)
print("Decrypted Message:", decrypted_message)
