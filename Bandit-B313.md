Pattern: Use of insecure `xml.etree.cElementTree` module

Issue: -

## Description

This module is not secure against maliciously constructed data. Use `defusedxml` package instead.

The results of an attack on a vulnerable XML library can be fairly dramatic. With just a few hundred Bytes of XML data an attacker can occupy several Gigabytes of memory within seconds. An attacker can also keep CPUs busy for a long time with a small to medium size request. Under some circumstances it is even possible to access local files on your server, to circumvent a firewall, or to abuse services to rebound attacks to third parties.

This rule checks for the following calls:

  - `xml.etree.cElementTree.parse`
  - `xml.etree.cElementTree.iterparse`
  - `xml.etree.cElementTree.fromstring`
  - `xml.etree.cElementTree.XMLParser`
  

Example of **insecure** code:

```python
import xml.etree.cElementTree as badET

xmlString = "<note>malicious data</note>"

# unsafe
tree = badET.fromstring(xmlString)
print(tree)
badET.parse('filethatdoesntexist.xml')
badET.iterparse('filethatdoesntexist.xml')
result = badET.XMLParser()
```

Example of **secure** code:

```python
import defusedxml.cElementTree as goodET

xmlString = "<note>malicious data</note>"

tree = goodET.fromstring(xmlString)
print(tree)
goodET.parse('filethatdoesntexist.xml')
goodET.iterparse('filethatdoesntexist.xml')
result = goodET.XMLParser()
```

## Further Reading

* [The Python Standard Library - xml.etree.ElementTree](https://docs.python.org/2/library/xml.etree.elementtree.html#module-xml.etree.ElementTree)
* [GitHub - defusedxml](https://github.com/tiran/defusedxml)
* [OpenStack - B313: xml_bad_cElementTree](https://docs.openstack.org/developer/bandit/api/bandit.blacklists.html#b313-b320-xml)
