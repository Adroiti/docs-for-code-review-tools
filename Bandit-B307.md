Pattern: Use of eval

Issue: -

## Description

Use of possibly insecure function - consider using safer ast.literal_eval.

This rule checks for the following calls:

  -

## Further Reading

* [OpenStack - B307: eval](https://docs.openstack.org/developer/bandit/api/bandit.blacklists.html#b307-eval)
