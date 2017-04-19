Pattern: SSL use with bad defaults specified

Issue: -

## Description

This plugin is part of a family of tests that detect the use of known bad
versions of SSL/TLS, please see [B502:
ssl_with_bad_version](ssl_with_bad_version.html) for a complete discussion.
Specifically, this rule scans for Python methods with default parameter
values that specify the use of broken SSL/TLS protocol versions. Currently,
detection supports methods using Python's native SSL/TLS support and the
pyOpenSSL module. A MEDIUM severity warning will be reported whenever known
broken protocol versions are detected.

```

## Further Reading:

  - [B502: ssl_with_bad_version](ssl_with_bad_version.html)
  - [B504: ssl_with_no_version](ssl_with_no_version.html)

**Config Options:**

This test shares the configuration provided for the standard [B502:
ssl_with_bad_version](ssl_with_bad_version.html) test, please refer to its
documentation.

Example of **incorrect** code:

```python

>> Issue: Function definition identified with insecure SSL/TLS protocol
version by default, possible security issue.
   Severity: Medium   Confidence: Medium
   Location: ./examples/ssl-insecure-version.py:28
27
28  def open_ssl_socket(version=SSL.SSLv2_METHOD):
29  pass

```

## Further Reading

  - <http://heartbleed.com/>
  - <https://poodlebleed.com/>
  - <https://security.openstack.org/>
  - <https://security.openstack.org/guidelines/dg_move-data-securely.html>
* [OpenStack - B503: ssl_with_bad_defaults](https://docs.openstack.org/developer/bandit/plugins/ssl_with_bad_defaults.html)
