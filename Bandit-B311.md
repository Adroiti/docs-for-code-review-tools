Pattern: Use of random

Issue: -

## Description

Standard pseudo-random generators are not suitable for security/cryptographic
purposes.

This rule checks for the following calls:

  - random.  - random.randrange
  - random.randint
  - random.choice
  - random.uniform
  - random.triangular

## Further Reading

* [OpenStack - B311: random](https://docs.openstack.org/developer/bandit/api/bandit.blacklists.html#b311-random)
