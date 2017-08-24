Pattern: Import of `xml.dom.pulldom` module

Issue: -

## Description

Using various methods to parse untrusted XML data is known to be vulnerable to
XML attacks. Replace vulnerable imports with the equivalent `defusedxml`
package, or make sure `defusedxml.defuse_stdlib()` is called.

## Further Reading

* [The Python Standard Library - xml.dom.pulldom](https://docs.python.org/2/library/xml.dom.pulldom.html)
* [GitHub - defusedxml](https://github.com/tiran/defusedxml)
* [OpenStack - B409: import_xml_pulldom](https://docs.openstack.org/developer/bandit/api/bandit.blacklists.html#b409-import-xml-pulldom)
