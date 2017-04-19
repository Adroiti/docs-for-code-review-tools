Pattern: Use of mktemp q

Issue: -

## Description

Use of insecure and deprecated function (mktemp).

This rule checks for the following calls:

  - tempfile.mktemp

## Further Reading

* [OpenStack - B306: mktemp_q](https://docs.openstack.org/developer/bandit/api/bandit.blacklists.html#b306-mktemp-q)
