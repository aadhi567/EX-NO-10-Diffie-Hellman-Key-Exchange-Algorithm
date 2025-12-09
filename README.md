# EX-NO-10-Diffie-Hellman-Key-Exchange-Algorithm

## AIM:
To Implement Diffie Hellman Key Exchange Algorithm 

## Algorithm:

1. Diffie-Hellman Key Exchange is used for securely sharing a secret key between two parties over an insecure channel.

2. Initialization: Agree on a large prime number \( p \) and a primitive root \( g \) modulo \( p \) (both are public values).

3. Key Exchange Process: 
   - Each party selects a private key and calculates their public key using the formula \( g^{\text{private key}} \mod p \).
   - Each party then shares their public key with the other.

4. Secret Key Computation: 
   - Each party computes the shared secret key using the received public key and their own private key.

5. Security: The difficulty of computing discrete logarithms ensures that the shared key remains secure even if public values are intercepted.

## Program:

```
#include <stdio.h>

long long int power(long long int base, long long int exp, long long int mod) {
    long long int res = 1;
    base = base % mod;
    while (exp > 0) {
        if (exp % 2 == 1)
            res = (res * base) % mod;
        base = (base * base) % mod;
        exp = exp / 2;
    }
    return res;
}

int main() {
    long long int P, G, x, a, y, b, ka, kb;
    
    printf("enter value of P:");
    scanf("%lld",&P);
    printf("enter value of G:");
    scanf("%lld",G);
    a = 4; 
    printf("Alice's Private Key: %lld\n", a);
    x = power(G, a, P); 
    printf("Alice sends Public Key: %lld\n", x);
    
    b = 3; 
    printf("Bob's Private Key: %lld\n", b);
    y = power(G, b, P); 
    printf("Bob sends Public Key: %lld\n", y);
    
    ka = power(y, a, P); 
    kb = power(x, b, P); 
    
    printf("Secret Key for Alice: %lld\n", ka);
    printf("Secret Key for Bob:   %lld\n", kb);
    
    return 0;
}
```



## Output:

<img width="633" height="349" alt="image" src="https://github.com/user-attachments/assets/4bfba204-72a7-4a05-a38b-833ca9407550" />





## Result:
  The program is executed successfully

