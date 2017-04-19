Pattern: Use of mark safe

Issue: -

## Description

Use of mark_safe() may expose cross-site scripting vulnerabilities and should
be reviewed.

This rule checks for the following calls:

  - django.utils.safestring.

## Further Reading

* [OpenStack - B308: mark_safe](https://docs.openstack.org/developer/bandit/api/bandit.blacklists.html#b308-mark-safe)
