Pattern: Use of possibly insecure `ftplib` module

Issue: -

## Description

FTP-related functions are being called. FTP was not designed to be a secure protocol, and has many security weaknesses. Use SSH, SFTP, SCP or some other encrypted protocol instead.

This rule checks for the following calls:

  - `ftplib.*`

## Further Reading

* [Wikipedia - File Transfer Protocol - Security](https://en.wikipedia.org/wiki/File_Transfer_Protocol#Security)
* [OpenStack - B321: ftplib](https://docs.openstack.org/developer/bandit/api/bandit.blacklists.html#b321-ftplib)
