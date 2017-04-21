Pattern: Use of insecure `xml.sax.expatreader` module

Issue: -

## Description

This module is not secure against maliciously constructed data. Use `defusedxml` package instead.

The results of an attack on a vulnerable XML library can be fairly dramatic. With just a few hundred Bytes of XML data an attacker can occupy several Gigabytes of memory within seconds. An attacker can also keep CPUs busy for a long time with a small to medium size request. Under some circumstances it is even possible to access local files on your server, to circumvent a firewall, or to abuse services to rebound attacks to third parties.


Example of **insecure** code:

```python
import xml.sax.expatreader as bad

result = bad.create_parser()
```

Example of **secure** code:

```python
import defusedxml.expatreader as good

result = good.create_parser()
```

## Further Reading

* [GitHub - defusedxml](https://github.com/tiran/defusedxml)
* [OpenStack - B315: xml_bad_expatreader](https://docs.openstack.org/developer/bandit/api/bandit.blacklists.html#b313-b320-xml)
