Pattern: Import of `xml.dom.minidom` module

Issue: -

## Description

Using various methods to parse untrusted XML data is known to be vulnerable to
XML attacks. Replace vulnerable imports with the equivalent `defusedxml`
package, or make sure `defusedxml.defuse_stdlib()` is called.

## Further Reading

* [The Python Standard Library - xml.dom.minidom](https://docs.python.org/2/library/xml.dom.minidom.html)
* [GitHub - defusedxml](https://github.com/tiran/defusedxml)
* [OpenStack - B408: import_xml_minidom](https://docs.openstack.org/developer/bandit/api/bandit.blacklists.html#b408-import-xml-minidom)
