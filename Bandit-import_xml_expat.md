Pattern: Use of import xml expat

Issue: -

## Description

Using various methods to parse untrusted XML data is known to be vulnerable to
XML attacks. Replace vulnerable imports with the equivalent defusedxml
package, or make sure defusedxml.defuse_stdlib() is called.

This rule checks for the following calls:

  - xml.dom.expatbuilder

## Further Reading

* [OpenStack - B407: import_xml_expat](https://docs.openstack.org/developer/bandit/api/bandit.blacklists.html#b407-import_xml_expat)
