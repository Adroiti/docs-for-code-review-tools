Pattern: Use of import xml sax

Issue: -

## Description

Using various methods to parse untrusted XML data is known to be vulnerable to
XML attacks. Replace vulnerable imports with the equivalent defusedxml
package, or make sure defusedxml.defuse_stdlib() is called.

This rule checks for the following calls:

  - xml.sax

## Further Reading

* [OpenStack - B406: import_xml_sax](https://docs.openstack.org/developer/bandit/api/bandit.blacklists.html#b406-import_xml_sax)
