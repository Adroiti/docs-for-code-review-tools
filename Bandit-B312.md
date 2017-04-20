Pattern: Use of `telnetlib` module

Issue: -

## Description

Telnet-related functions are being called. Telnet is considered insecure protocol because of serious security concerns when using over an open network such as the Internet. Use SSH or some other encrypted protocol.

This rule checks for the following calls:

  - `telnetlib.*`

## Further Reading

* [Wikipedia - Telnet(https://en.wikipedia.org/wiki/Telnet#Security)
* [The Python Language Reference - telnetlib](https://docs.python.org/2/library/telnetlib.html)
* [OpenStack - B312: telnetlib](https://docs.openstack.org/developer/bandit/api/bandit.blacklists.html#b312-telnetlib)
