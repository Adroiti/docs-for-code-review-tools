Pattern: SSL use with no version specified

Issue: -

## Description

This plugin is part of a family of tests that detect the use of known bad
versions of SSL/TLS, please see [B502:
ssl_with_bad_version](ssl_with_bad_version.html) for a complete discussion.
Specifically, This rule scans for specific methods in Python's native
SSL/TLS support and the pyOpenSSL module that configure the version of SSL/TLS
protocol to use. These methods are known to provide default value that
maximize compatibility, but permit use of the aforementioned broken protocol
versions. A LOW severity warning will be reported whenever this is detected.

```

## Further Reading:

  - [B502: ssl_with_bad_version](ssl_with_bad_version.html)
  - [B503: ssl_with_bad_defaults](ssl_with_bad_defaults.html)

**Config Options:**

This test shares the configuration provided for the standard [B502:
ssl_with_bad_version](ssl_with_bad_version.html) test, please refer to its
documentation.

Example of **incorrect** code:

```python

>> Issue: ssl.wrap_socket call with no SSL/TLS protocol version
specified, the default SSLv23 could be insecure, possible security
issue.
   Severity: Low   Confidence: Medium
   Location: ./examples/ssl-insecure-version.py:23
22
23  ssl.wrap_socket()
24

```

## Further Reading

  - <http://heartbleed.com/>
  - <https://poodlebleed.com/>
  - <https://security.openstack.org/>
  - <https://security.openstack.org/guidelines/dg_move-data-securely.html>
* [OpenStack - B504: ssl_with_no_version](https://docs.openstack.org/developer/bandit/plugins/ssl_with_no_version.html)
