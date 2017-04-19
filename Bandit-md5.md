Pattern: Use of md5

Issue: -

## Description

Use of insecure MD2, MD4, or MD5 hash function.

This rule checks for the following calls:

  - hashlib.  - Crypto.Hash.MD2.new
  - Crypto.Hash.MD4.new
  - Crypto.Hash.MD5.new
  - Cryptodome.Hash.MD2.new
  - Cryptodome.Hash.MD4.new
  - Cryptodome.Hash.MD5.new
  - cryptography.hazmat.primitives .hashes.MD5

## Further Reading

* [OpenStack - B303: md5](https://docs.openstack.org/developer/bandit/api/bandit.blacklists.html#b303-md5)
