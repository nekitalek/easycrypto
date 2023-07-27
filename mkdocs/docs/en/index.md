# Cryptography, understandable to everyone

This repository is also available in [russian](readme.ru.md).

The purpose of this book is to simplify difficult-to-understand cryptography so that as many people as possible can become familiar with cryptography and become interested in it. To read this book, you need to have a certain mathematical theoretical base. This book contains theoretical and practical parts with simple implementations of algorithms and primitives, which are described in this repository.

This book is under writing. The book will always follow the development of cryptographic technologies and will be updated at any time. The content may be inconsistent. I hope the readers will forgive me. Because of the far from flawless level of the author who wrote this book, if there are any doubts in the book, you can describe them and discuss them together.

**I invite everyone to contribute!**

## Repository Content

```css
├── README.md
├── primitives/
|   ├── signing.py
│   └── README.md
├── asymmetric/
|   ├── ECC.py
|   ├── Elgamal.py
|   ├── GOST 34.10.py
|   ├── Luc.py
|   ├── RSA.py
│   └── README.md
├── symmetric/
|   ├── 3DES.py
|   ├── AES.py
|   ├── Kuznechik.py
|   ├── RC4.py
|   ├── RC5.py
│   └── README.md
├── hash-functions/
|   ├── CRC32.py
|   ├── MD5.py
|   ├── SHA-256.py
│   └── README.md
├── quantum/
|   ├── BB84.py
|   ├── Bennet.py
│   └── README.md
└── post-quantum/
    ├── error-code-based.py
    ├── esogeny-based.py
    ├── hash-based.py
    ├── lattice-based.py
    └── README.md
```
