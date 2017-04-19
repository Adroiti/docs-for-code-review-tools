Pattern: Use of import lxml

Issue: -

## Description

Using various methods to parse untrusted XML data is known to be vulnerable to
XML attacks. Replace vulnerable imports with the equivalent defusedxml
package.

This rule checks for the following calls:

  - lxml

## Further Reading

* [OpenStack - B410: import_lxml](https://docs.openstack.org/developer/bandit/api/bandit.blacklists.html#b410-import-lxml)
