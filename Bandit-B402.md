Pattern: Import of `ftplib` module

Issue: -

## Description

A FTP-related module is being imported. FTP was not designed to be a secure protocol, and has many security weaknesses. Use SSH, SFTP, SCP or some other encrypted protocol instead.

## Further Reading

* [Wikipedia - File Transfer Protocol - Security](https://en.wikipedia.org/wiki/File_Transfer_Protocol#Security)
* [OpenStack - B402: inport_ftplib](https://docs.openstack.org/developer/bandit/api/bandit.blacklists.html#b402-import-ftplib)
