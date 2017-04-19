Pattern: Use of cipher modes

Issue: -

## Description

ciphers and modes

Use of insecure cipher or cipher mode. Replace with a known secure cipher such
as AES.

This rule checks for the following calls:

B304

ciphers

  - Crypto.Cipher.ARC2.new
  - Crypto.Cipher.ARC4.new
  - Crypto.Cipher.Blowfish.new
  - Crypto.Cipher.DES.new
  - Crypto.Cipher.XOR.new
  - Cryptodome.Cipher.ARC2.new
  - Cryptodome.Cipher.ARC4.new
  - Cryptodome.Cipher.Blowfish.new
  - Cryptodome.Cipher.DES.new
  - Cryptodome.Cipher.XOR.new
  - cryptography.hazmat.primitives .ciphers.algorithms.ARC4
  - cryptography.hazmat.primitives .ciphers.algorithms.Blowfish
  - cryptography.hazmat.primitives .ciphers.algorithms.IDEA

  - cryptography.hazmat.primitives .ciphers.modes.ECB

## Further Reading

* [OpenStack - B305: cipher_modes](https://docs.openstack.org/developer/bandit/api/bandit.blacklists.html#b304-b305-ciphers-and-modes)
