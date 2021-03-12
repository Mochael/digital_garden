---
title: How Quantum Computers Could Quickly Break Encription
tree_state: 🌱
---

## Primer on Encryption with Prime Numbers
The way things are encrypted today is to use public and private keys. A public key is created by generating two massive prime numbers, and each public key is unique. The private key is just one of those prime numbers.
How they are used:
1. Say Jason wants to send an encrypted message to Jessica.
2. Jason fetches Jessica's public key and inputs it into a cryptographic hash function along with his message.
3. Jason sends the message to Jessica, who can only read it if she inputs her private key into the decryption algorithm. Encryption only requires public key, whereas decryption requires a private key.

So if someone wanted to read the message, they would need to compute Jessica's private key $A$ by factoring the public key $N$. Let's try to hack open this message.

## Decrypting the Message
To create Jessica's public key, say she multiple two prime numbers $A$ and $B$ together to get $N$, where $A$ is her private key. So, we are given $N$, but we need $A$. Let's try the following strategy to get $A$.

1. Guess a random positive integer $g$
2. We want to find a positive, even prime number $p$ such that: $g^p \bmod N = 1$ or $g^p = mN+1$ where $m$ is some positive integer. This number exists as long as $g$ and $N$ are coprime (proof below).
3. Once we find $p$, we calculate $(A^{p/2}+1)(A^{p/2}-1) = mN$.
	- if $p$ is even and both $(A^{p/2}+1)$ and $(A^{p/2}-1)$ are not multiples of $N$, then we know that $(A^{p/2}+1)$ and $(A^{p/2}-1)$ must contain factors of $N$.
	- Therefore, they contain $A$ and $B$ as factors
	- 37.5% of the time, these conditions are met from a random guess of $g$
4. We can find the common factors between  $(A^{p/2}+1)$, $(A^{p/2}-1)$, and $N$ to get the values of $A$ and $B$.


#### Complexity in decryption stems from getting the right $p$.
Look at Proof #2 : https://en.wikipedia.org/wiki/Euler's_theorem#Proofs
- Basically if you have a set of values abiding by these https://en.wikipedia.org/wiki/Reduced_residue_system conditions, then if you multiply the set by some constant that's coprime to $N$ ($n$ in Wiki), the set of values will have the same modulo/remainder values, although they may be in a different order.
- Then with some algebra manipulation, you can show that after multiplying this constant by itself totient(N) times, it will have a remainder of 1 when divided by $N$.


### Use a Quantum Computer
1. Guess a random positive integer $g$
2. Create quantum state which a value for every possible guess of $p$ (let's call each of these guesses $i$) and the corresponding value of $g^i\bmod N$ for that guess (<$i$, $g^i \bmod N$)
	- Notice that $g^p \bmod N = 1$ and thus multiplying/dividing $g^p$ by any power of $g$, will result in the same remainder $\bmod N$. For example, suppose $g^x \bmod N = 7$, then $g^{x+3p} \bmod N = 7$
	- So, $g^p$ is actually the smallest unit of distance we can move from $g^x$ to reach the next value with $g$ as the base that has the same remainder/modulo.
	- This means that if we take only the set of guesses for $p$ in the quantum state that have a remainder/modulo of $7$, the distance between these guesses $i$ will be $p$. For example, we would have values in the state of <6,7>, <15,7>, <24,7>,..., which would mean that $p=9$ (the distance between each $i$).
	- This is equivalent to a wave with a period of $p$ (frequency of $1/p$). So, using a quantum computer where we want to get rid of the states that don't match the same values of $g^i \bmod N$, we can input this into the quantum equivalent of a Fourier transform to then just have as output, frequency of the wave, which gives us the value of $p$.
	
Now we $p$ and so we can calculate the private key!


### Real RSA Encryption
http://mathonline.wikidot.com/rsa-encryption#toc0