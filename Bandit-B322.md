Pattern: Use of input

Issue: -

## Description

The input method in Python 2 will read from standard input, evaluate and run
the resulting string as python source code. This is similar, though in many
ways worse, then using eval. On Python 2, use raw_input instead, input is safe
in Python 3.

This rule checks for the following calls:

  -

## Further Reading

* [OpenStack - B322: input](https://docs.openstack.org/developer/bandit/api/bandit.blacklists.html#b322-input)
