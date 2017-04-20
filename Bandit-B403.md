Pattern: Import of `pickle` module

Issue: -

## Description

This module not secure against erroneous or maliciously constructed data. Consider possible security implications before use.

This rule checks for the following imports:

  - pickle
  - cPickle

## Further Reading

* [The Python Language Reference - pickle](https://docs.python.org/2/library/pickle.html)
* [OpenStack - B403: import_pickle](https://docs.openstack.org/developer/bandit/api/bandit.blacklists.html#b403-import-pickle)
