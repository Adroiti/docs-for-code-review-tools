Pattern: Use of marshal

Issue: -

## Description

Deserialization with the marshal module is possibly dangerous.

This rule checks for the following calls:

  - marshal.load
  - marshal.loads

## Further Reading

* [OpenStack - B302: marshal](https://docs.openstack.org/developer/bandit/api/bandit.blacklists.html#b302-marshal)
