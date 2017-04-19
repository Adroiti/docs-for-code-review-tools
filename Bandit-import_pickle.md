Pattern: Use of import pickle

Issue: -

## Description

Consider possible security implications associated with these modules.

This rule checks for the following calls:

  - pickle
  - cPickle

## Further Reading

* [OpenStack - B403: import_pickle](https://docs.openstack.org/developer/bandit/api/bandit.blacklists.html#b403-import_pickle)
