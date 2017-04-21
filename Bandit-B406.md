Pattern: Import of `xml.sax` module

Issue: -

## Description

Using various methods to parse untrusted XML data is known to be vulnerable to
XML attacks. Replace vulnerable imports with the equivalent `defusedxml`
package, or make sure `defusedxml.defuse_stdlib()` is called.

## Further Reading

* [The Python Standard Library - xml.sax](https://docs.python.org/2/library/xml.sax.html)
* [GitHub - defusedxml](https://github.com/tiran/defusedxml)
* [OpenStack - B406: import_xml_sax](https://docs.openstack.org/developer/bandit/api/bandit.blacklists.html#b406-import-xml-sax)
