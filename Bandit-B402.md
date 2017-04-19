Pattern: Use of import ftplib

Issue: -

## Description

A FTP-related module is being imported. FTP is considered insecure. Use
SSH/SFTP/SCP or some other encrypted protocol.

This rule checks for the following calls:

inport_ftplib

  - ftplib

## Further Reading

* [OpenStack - B402: import_ftplib](https://docs.openstack.org/developer/bandit/api/bandit.blacklists.html#b402-import-ftplib)
