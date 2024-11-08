def sieve_of_eratosthenes(n):
    primes = [True] * (n + 1)
    p = 2
    while (p * p <= n):
        if primes[p]:
            for i in range(p * p, n + 1, p):
                primes[i] = False
        p += 1
    prime_numbers = [p for p in range(2, n + 1) if primes[p]]
    return prime_numbers

# List prime numbers from 1 to 100
prime_numbers = sieve_of_eratosthenes(100)
print("Prime numbers from 1 to 100 are:", prime_numbers)
