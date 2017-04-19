Pattern: Use of telnetlib

Issue: -

## Description

Telnet-related functions are being called. Telnet is considered insecure. Use
SSH or some other encrypted protocol.

This rule checks for the following calls:

  - telnetlib.*

## Further Reading

* [OpenStack - B312: telnetlib](https://docs.openstack.org/developer/bandit/api/bandit.blacklists.html#b312-telnetlib)
