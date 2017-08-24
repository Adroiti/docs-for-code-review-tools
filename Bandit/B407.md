Pattern: Import of `xml.dom.expatbuilder` module

Issue: -

## Description

Using various methods to parse untrusted XML data is known to be vulnerable to XML attacks. Replace vulnerable imports with the equivalent `defusedxml` package, or make sure `defusedxml.defuse_stdlib()` is called.

## Further Reading

* [GitHub - defusedxml](https://github.com/tiran/defusedxml)
* [OpenStack - B407: import_xml_expat](https://docs.openstack.org/developer/bandit/api/bandit.blacklists.html#b407-import-xml-expat)
