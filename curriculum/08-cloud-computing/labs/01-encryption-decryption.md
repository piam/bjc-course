---
layout: page
title: Encryption and Decryption
unit: 8
uniturl: 08-cloud-computing
lab: 1
laburl: 01-encryption-decryption
---


Encryption and Decryption
=========================
Learning Objective 27: The student can connect the concern of cybersecurity with the Internet and systems built on it.

 * 27a. Identification of tradeoffs associated with the trust model of the Internet.
 * 27b. Description of software, hardware, and human components involved in implementing cybersecurity.
 * 27c. Explanation of how cryptography is essential to many models of cybersecurity.

Symmetric Key Cryptography
--------------------------
**Cryptography** means secret writing. **Cryptanalysis** is the study of how to break a secret message, sometimes called a **cryptogram**.

A **cipher** is system for **encrypting** and **decrypting** messages. A cipher's strength -- i.e., how secure it is, how well it protects a secret message -- depends on the strength and security of its key.

A *symmetric* key cipher is one in which the sender and receiver of the message share the same secret key.

Simple Substitution Cipher
--------------------------
A **simple substitution cipher** is a cipher that is based on a **permutation** of the alphabet. For example,

Plaintext alphabet:   abcdefghijklmnopqrstuvwxyz

Cipher alphabet   :   **ZEBRASROCK**DFGHIJLMNPQTUVWX

There are 26! (= 4.03291461 × 10<sup>26</sup>) ways to permute a 26-letter alphabet -- i.e, 26 ways to pick the first letter times 25 ways to pick the second times 24 ways to pick the third, and so on.

In this example, the *symmetric key* is the permuted cipher alphabet. Note how we can use the *keyphrase*, "zebras rock" to construct the alphabet. This makes it easier for two parties to share a secret key.

If Alice wants to send the secret message "attack at noon" to Bob, her fellow agent, should would use the cipher alphabet to encrypt the message, replacing a with Z, t with P, and so on:

Plaintext alphabet:   abcdefghijklmnopqrstuvwxyz

Cipher alphabet   :   ZEBRASROCKDFGHIJLMNPQTUVWX

                      attack at noon

                      ZPPZBD ZP HIIH

Upon receipt of the message, Bob would use the cipher alphabet in reverse to decrypt the message, replace Z with a, P with t, and so on:

Plaintext alphabet:   abcdefghijklmnopqrstuvwxyz

Cipher alphabet   :   ZEBRASROCKDFGHIJLMNPQTUVWX

                      ZPPZBD ZP HIIH

                      attack at noon


Breaking a Cipher
-----------------
Suppose Eve intercepts Alice's message. Eve doesn't know the key. Can she break the secret message?

**Question:** Would it be practical to try every one of the 26! alphabets? No, that would be **intractable**.

If Alice and Bob only sent short messages and changed their key after every message -- i.e., **one-time pad** -- then Eve will not be able to crack the messages.

But, if they use the key to send message of 40 or more characters, then Eve may be able to break it using **pattern analysis** and **frequency analysis**. How many English words have the pattern 1221 (noon, kook, deed, ...)? If the letter "t" is the second most frequent letter in English, then its substitute, "P", will be the second most frequent letter in the secret message.


Modern Symmetric Cipher
-----------------------
The [Advanced Encryption Standard (AES)](http://en.wikipedia.org/wiki/Advanced_Encryption_Standard) is a modern secure electronic cipher used by businesses and the federal government.

AES is an open standard that went through a 5 year public analysis period. AES turns documents into strings of bits and then scrambles and permutes the bits in such a way that it removes all statistical patterns.

What makes AES secure is its large key size, ranging from 128, 192, or 256 bits, which make it **intractable** to use a brute-force search to find the key.


The Key Exchange Problem
------------------------
How can Alice and Bob share their shared key? It's difficult to image the modern day Internet if the **key exchange problem** had not been solved.




Public Key Cryptography
-----------------------
In **public key cryptography** the key exchange problem goes away because there is no secret key to be shared.

It is based on a **trap door function** or a **one way function** -- i.e., a function that is easy to compute in one direction but hard (intractable) to compute in the other.

For example, its easy to multiply 2180 × 7208 = 15,713,440. But it would be relatively difficult to factor 15,713,440 into 2180 and 7208.


Simple Public Key Example
-------------------------
Here's a [simple example](http://www.di-mgt.com.au/rsa_alg.html#simpleexample) of the Rivest Shamir Adelman (RSA) public key algorithm. It illustrates that we can send a secret message without having to share a secret key.

 * Pick two big (100 digit) prime numbers, p = 11, q = 3
 * Let n = p × q = 11 × 3 = 33
 * Let phi = (p - 1) × (q - 1) = 20
 * Choose e=3 to be relatively prime to (p - 1) and (q - 1) -- i.e., gcd(10,3) = 1 and gcd(2,3) = 1.
 * Find d=7 such that phi (20) divides (3 × d) - 1 -- i.e., 20 = (3 × 7) - 1
 * We end up with 3 numbers, n, e, and d that can be used to form Alice's public and private keys:
    
Alice's **public key**: (n, e) = (33, 3) Alice publishes this key.

Alice's **private key**: (n, d) = (33, 7) Alice keeps this key secret.

Let's suppose Bob wants to send the message "15" to Alice.

Bob encrypts the message using Alice's public key: 153 mod 33 = 3375 mod 33 = 9

Alice receives the secret message, "9".

Alice decrypts the message using her private key: 97 mod 33 = 4782969 mod 33 = 15

Alice reads Bob's message, "15".

What makes RSA secure is that it's easy to compute c = m<sup>e</sup> mod n, but it's very difficult to compute its inverse -- i.e., m = c<sup>-e</sup> mod n.


Secure Transactions Across the Internet
---------------------------------------
In **secure client-server** transactions, RSA is used by the client (Alice) and server (Bob) to exchange a **secret symmetric key**.

Note the role that the **certificate** plays in authenticating the identity of the server.

Questions
---------
 * Would it be possible to have today's Internet -- Amazon, online banking, etc. -- without public key cryptography?
 * Can you solve this simple substitution cryptogram?

Qbono kjdo vrp r lcqdbon rq Qncjcqy,

Vbkpo xrpqerhh vrp dhkdgos rq cjxcjcqy.

Kj sryp bo vkths lcqdb,

Qbo erqqonp vkths scqdb,

Pk bcqp vono rj cilkppcechcqy.

 * Hint: Look at the first words in lines 1 and 3.
 * Hint: That first word has a familiar pattern.
 * Hint: The last word in the first line has a familiar pattern.
 * Here's an [online cryptogram tool](http://www.cs.trincoll.edu/~ram/cryptogrammer/) to help you solve it. Paste the cryptogram into the tool and then try substituting letters in the alphabet until you get it.

