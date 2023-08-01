[# Symmetric Cryptography
Currently, all existing cryptosystems are divided into two classes: _symmetric_ and _asymmetric_.

Accordingly, they talk about symmetric cryptography and asymmetric cryptography.

__In symmetric cryptosystems__ both encryption and decryption are performed with the same secret key:

$$E_k(P) = C$$
$$D_k(C) = P$$

where $E$ is the encryption function, $k$ is the key, $P$ is the plaintext, $C$ is the ciphertext,
$D$ is the decryption function.

In this case , the following equality is true:
$$D_k(E_k(P)) = P$$

__threaded and block ciphers__

Algorithms that process plaintext bitwise are called __stream algorithms__ or stream ciphers.

Algorithms that process groups of bits (blocks) of plaintext are called __block algorithms__ or block ciphers.

For a long time in computer algorithms, the typical block size was 64 bits. This is a large enough value to make analysis difficult, and at the same time small enough to be convenient for work. Currently, 128-bit blocks are used, since the block length of 64 bits does not meet modern requirements for the efficiency and reliability of algorithms.

The most widely used symmetric cryptosystems in practice for a long time were the DES (US standard), IDEA (European standard), GOST (RF standard) systems and their modifications.

## Block ciphers

### The principle of construction

Let the encrypted message be represented as a sequence of zeros and ones. If, before encryption, this sequence
is divided into blocks of fixed length 𝑛 and then each block
is encrypted separately, then such encryption is called __block__.

![Block Encryption](image.png)

It is customary to call each block an open text (plaintext) and denote it by $𝑃$. The block size is usually several tens of bits (for example, 64, 128, 256 bits). The _key (key) $𝐾$ is a secret sequence of bits of length $𝑚$ used when encrypting a certain (sufficiently large) number of blocks. Modern key lengths are, for example, 128, 256, 512 bits. A block cipher consists of several rounds, at each of which there is a reversible transformation of a block of length $𝑛$ into a new block of the same length. The output block of the $𝑖$ round is called an intermediate ciphertext and is denoted by $𝐶_$. It is the input block of the next $𝑖 +1$ round. The input block of the first round is $𝐶 _0 = 𝑃$._ ciphertext (ciphertext) $𝐶$ is the output block of the last round, $𝐶 = 𝐶_$. The number of rounds of $𝑟$ (in practice, from 8 to 64) should be, on the one hand, large enough to ensure high cryptographic strength of the cipher, and on the other hand, small enough for encryption to be fast. Often, the same transformation is used on all rounds of the cipher, depending only on different bits of the key. Namely, $𝑟$_podkey is formed from the key $𝐾_1, . . . , 𝐾_𝑟$, each of which is used on
a specific round.](readme.md)
