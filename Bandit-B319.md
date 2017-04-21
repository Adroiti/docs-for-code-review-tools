Pattern: Use of insecure `xml.dom.pulldom` module

Issue: -

## Description

This module is not secure against maliciously constructed data. Use `defusedxml` package instead.

The results of an attack on a vulnerable XML library can be fairly dramatic. With just a few hundred Bytes of XML data an attacker can occupy several Gigabytes of memory within seconds. An attacker can also keep CPUs busy for a long time with a small to medium size request. Under some circumstances it is even possible to access local files on your server, to circumvent a firewall, or to abuse services to rebound attacks to third parties.

This rule checks for the following calls:

  - `xml.dom.pulldom.parse`
  - `xml.dom.pulldom.parseString`


Example of **insecure** code:

```python
from xml.dom.pulldom import parseString as badParseString

result = badParseString("<myxml>malicious data/myxml>")
print(result)
```

Example of **secure** code:

```python
from defusedxml.pulldom import parseString as goodParseString

result = goodParseString("<myxml>malicious data/myxml>")
print(result)
```

## Further Reading

* [The Python Standard Library - xml.dom.pulldom](https://docs.python.org/2/library/xml.dom.pulldom.html)
* [GitHub - defusedxml](https://github.com/tiran/defusedxml)
* [OpenStack - B319: xml_bad_pulldom](https://docs.openstack.org/developer/bandit/api/bandit.blacklists.html#b313-b320-xml)
