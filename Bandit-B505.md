Pattern: Use of weak cryptographic key

Issue: -

## Description

As computational power increases, so does the ability to break ciphers with
smaller key lengths. The recommended key length size for RSA and DSA
algorithms is 2048 and higher. 1024 bits and below are now considered
breakable. EC key length sizes are recommended to be 224 and higher with 160
and below considered breakable. This rule checks for use of any key
less than those limits.


Example of **insecure** code:

```python
from cryptography.hazmat import backends
from cryptography.hazmat.primitives.asymmetric import dsa

dsa.generate_private_key(key_size=1024, backend=backends.default_backend())
```

Example of **secure** code:

```python
from cryptography.hazmat import backends
from cryptography.hazmat.primitives.asymmetric import dsa

dsa.generate_private_key(key_size=2048, backend=backends.default_backend())
```

## Further Reading

* [NIST - Transitions: Recommendation for Transitioning the Use of Cryptographic Algorithms and Key Lengths](http://nvlpubs.nist.gov/nistpubs/Legacy/SP/nistspecialpublication800-131a.pdf)
* [OpenStack - Use Strong and Established Cryptographic Elements](https://security.openstack.org/guidelines/dg_strong-crypto.html)
* [OpenStack - B505: weak_cryptographic_key](https://docs.openstack.org/developer/bandit/plugins/weak_cryptographic_key.html)
