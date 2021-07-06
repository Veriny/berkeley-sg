# Cryptography/RSA

## Fermat's Little Theorem

The theorem states that for any prime p and any number $$a \in \{1, ... p-1\}$$ we have that $$a^{p - 1} \equiv 1 \text{ mod }p.$$ 

## RSA

RSA starts off with two primes, $$p$$ and $$q.$$

We have $$N:= pq$$ and a number $$e$$ such that $$\text{gcd}(e, (p - 1)(q-1)) = 1.$$ Our private key is $$d:= e^{-1}(\text{mod} (p - 1)(q - 1))$$ 

### Encryption

$$
E(x) = x^e \text{mod } N
$$

### Decrpytion

$$
D(x) = y^d \text{mod } N
$$

