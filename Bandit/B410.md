Pattern: Import of `lxml` module

Issue: -

## Description

Using various methods to parse untrusted XML data is known to be vulnerable to
XML attacks. Replace vulnerable imports with the equivalent `defusedxml` package.

## Further Reading

* [GitHub - defusedxml](https://github.com/tiran/defusedxml)
* [OpenStack - B410: import_lxml](https://docs.openstack.org/developer/bandit/api/bandit.blacklists.html#b410-import-lxml)
