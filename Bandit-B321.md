Pattern: Use of ftplib

Issue: -

## Description

FTP-related functions are being called. FTP is considered insecure. Use
SSH/SFTP/SCP or some other encrypted protocol.

This rule checks for the following calls:

  - ftplib.*

## Further Reading

* [OpenStack - B321: ftplib](https://docs.openstack.org/developer/bandit/api/bandit.blacklists.html#b321-ftplib)
