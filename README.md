def sieve_of_eratosthenes(limit):
    primes = [True] * (limit + 1)
    primes[0], primes[1] = False, False  # 0 and 1 are not prime numbers
     
    for num in range(2, int(limit**0.5) + 1):
        if primes[num]:
            for multiple in range(num * num, limit + 1, num):
                primes[multiple] = False
                
    
    return [num for num, is_prime in enumerate(primes) if is_prime]

if __name__ == "__main__":
    limit = int(input("Enter the upper limit to find prime numbers: "))
    prime_numbers = sieve_of_eratosthenes(limit)
    print(f"Prime numbers up to {limit}: {prime_numbers}")

# simple-calculator
