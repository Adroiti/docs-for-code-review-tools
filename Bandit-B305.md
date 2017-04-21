Pattern: Use of insecure cipher mode

Issue: -

## Description

Insecure cipher mode could be possibly dangerous and should be replaced with a better alternative.

The main reason not to use ECB mode encryption is that it's not semantically secure — that is, merely observing ECB-encrypted cipher-text can leak information about the plain text (even beyond its length, which all encryption schemes accepting arbitrarily long plain texts will leak to some extent). You should instead use any authenticated encryption mode, such as GCM, EAX or OCB.

This rule checks for the following calls:

  - `cryptography.hazmat.primitives.ciphers.modes.ECB`

## Further Reading

* [NIST - Proposed Modes](http://csrc.nist.gov/groups/ST/toolkit/BCM/modes_development.html)
* [OpenStack - B305: cipher_modes](https://docs.openstack.org/developer/bandit/api/bandit.blacklists.html#b304-b305-ciphers-and-modes)
