Pattern: Use of xml bad expatreader

Issue: -

## Description

XML

Most of this is based off of Christian Heimes’ work on defusedxml:
<https://pypi.python.org/pypi/defusedxml/#defusedxml-sax>

Using various XLM methods to parse untrusted XML data is known to be
vulnerable to XML attacks. Methods should be replaced with their defusedxml
equivalents.

This rule checks for the following calls:

B313

xml_bad_cElementTree

  - xml.etree.cElementTree.parse
  - xml.etree.cElementTree.iterparse
  - xml.etree.cElementTree.fromstring
  - xml.etree.cElementTree.XMLParser

B314

xml_bad_ElementTree

  - xml.etree.ElementTree.parse
  - xml.etree.ElementTree.iterparse
  - xml.etree.ElementTree.fromstring
  - xml.etree.ElementTree.XMLParser

  - xml.sax.expatreader.create_parser

B316

xml_bad_expatbuilder

  - xml.dom.expatbuilder.parse
  - xml.dom.expatbuilder.parseString

B317

xml_bad_sax

  - xml.sax.parse
  - xml.sax.parseString
  - xml.sax.make_parser

B318

xml_bad_minidom

  - xml.dom.minidom.parse
  - xml.dom.minidom.parseString

B319

xml_bad_pulldom

  - xml.dom.pulldom.parse
  - xml.dom.pulldom.parseString

B320

xml_bad_etree

  - lxml.etree.parse
  - lxml.etree.fromstring
  - lxml.etree.RestrictedElement
  - lxml.etree.GlobalParserTLS
  - lxml.etree.getDefaultParser
  - lxml.etree.check_docinfo

## Further Reading

* [OpenStack - B315: xml_bad_expatreader](https://docs.openstack.org/developer/bandit/api/bandit.blacklists.html#b313-b320-xml)
