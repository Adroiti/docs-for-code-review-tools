Pattern: Use of import telnetlib

Issue: -

## Description

A telnet-related module is being imported. Telnet is considered insecure. Use
SSH or some other encrypted protocol.

This rule checks for the following calls:

  - telnetlib

## Further Reading

* [OpenStack - B401: import_telnetlib](https://docs.openstack.org/developer/bandit/api/bandit.blacklists.html#b401-import-telnetlib)
