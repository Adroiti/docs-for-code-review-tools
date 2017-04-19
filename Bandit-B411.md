Pattern: Use of import xmlrpclib

Issue: -

## Description

XMLRPC is particularly dangerous as it is also concerned with communicating
data over a network. Use defused.xmlrpc.monkey_patch() function to monkey-
patch xmlrpclib and mitigate remote XML attacks.

This rule checks for the following calls:

  - xmlrpclib

## Further Reading

* [OpenStack - B411: import_xmlrpclib](https://docs.openstack.org/developer/bandit/api/bandit.blacklists.html#b411-import-xmlrpclib)
