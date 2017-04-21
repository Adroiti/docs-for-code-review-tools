Pattern: Import of `xmlrpclib` module

Issue: -

## Description

XMLRPC is particularly dangerous as it is also concerned with communicating data over a network. Use `defused.xmlrpc.monkey_patch()` function to monkey-patch `xmlrpclib` and mitigate remote XML attacks.

## Further Reading

* [The Python Standard Library - xmlrpclib](https://docs.python.org/2/library/xmlrpclib.html)
* [OpenStack - B411: import_xmlrpclib](https://docs.openstack.org/developer/bandit/api/bandit.blacklists.html#b411-import-xmlrpclib)
