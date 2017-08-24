Pattern: Use of insecure or sub-optimal cipher

Issue: -

## Description

Insecure or sub-optimal cipher could be possibly dangerous and should be replaced with a better alternative such as `AES`. For example, 
`DES` is now considered insecure because a brute force attack is possible. `DES` module in `Cipher` package is provided only for legacy purposes with recommendation to use `AES` instead.

Use the following table to replace legacy cipher:

| From  | To |
| ------------- | ------------- |
| ARC2  | AES  |
| ARC4  | ChaCha20  |
| Blowfish  | AES  |
| DES  | AES  |
| IDEA  | AES  |

This rule checks for the following calls:

  - `Crypto.Cipher.ARC2.new`
  - `Crypto.Cipher.ARC4.new`
  - `Crypto.Cipher.Blowfish.new`
  - `Crypto.Cipher.DES.new`
  - `Crypto.Cipher.XOR.new`
  - `Cryptodome.Cipher.ARC2.new`
  - `Cryptodome.Cipher.ARC4.new`
  - `Cryptodome.Cipher.Blowfish.new`
  - `Cryptodome.Cipher.DES.new`
  - `Cryptodome.Cipher.XOR.new`
  - `cryptography.hazmat.primitives.ciphers.algorithms.ARC4`
  - `cryptography.hazmat.primitives.ciphers.algorithms.Blowfish`
  - `cryptography.hazmat.primitives.ciphers.algorithms.IDEA`

## Further Reading

* [Crypto - Package Cipher](http://legrandin.github.io/pycryptodome/Doc/3.4/Crypto.Cipher-module.html)
* [OpenStack - B304: ciphers](https://docs.openstack.org/developer/bandit/api/bandit.blacklists.html#b304-b305-ciphers-and-modes)
