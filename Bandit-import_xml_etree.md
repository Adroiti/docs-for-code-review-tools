Pattern: Use of import xml etree

Issue: -

## Description

Using various methods to parse untrusted XML data is known to be vulnerable to
XML attacks. Replace vulnerable imports with the equivalent defusedxml
package, or make sure defusedxml.defuse_stdlib() is called.

This rule checks for the following calls:

  - xml.etree.cElementTree
  - xml.etree.ElementTree

## Further Reading

* [OpenStack - B405: import_xml_etree](https://docs.openstack.org/developer/bandit/api/bandit.blacklists.html#b405-import_xml_etree)
