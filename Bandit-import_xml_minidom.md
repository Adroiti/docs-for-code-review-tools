Pattern: Use of import xml minidom

Issue: -

## Description

Using various methods to parse untrusted XML data is known to be vulnerable to
XML attacks. Replace vulnerable imports with the equivalent defusedxml
package, or make sure defusedxml.defuse_stdlib() is called.

This rule checks for the following calls:

  - xml.dom.minidom

## Further Reading

* [OpenStack - B408: import_xml_minidom](https://docs.openstack.org/developer/bandit/api/bandit.blacklists.html#b408-import_xml_minidom)
