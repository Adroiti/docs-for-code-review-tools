Pattern: Use of import xml pulldom

Issue: -

## Description

Using various methods to parse untrusted XML data is known to be vulnerable to
XML attacks. Replace vulnerable imports with the equivalent defusedxml
package, or make sure defusedxml.defuse_stdlib() is called.

This rule checks for the following calls:

  - xml.dom.pulldom

## Further Reading

* [OpenStack - B409: import_xml_pulldom](https://docs.openstack.org/developer/bandit/api/bandit.blacklists.html#b409-import_xml_pulldom)
