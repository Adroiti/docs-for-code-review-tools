Pattern: Use of `HTTPSConnection`

Issue: -

## Description

Use of `HTTPSConnection` on older versions of Python prior to `2.7.9` and `3.4.3` do not provide security. The `Requests` package is recommended for a higher-level HTTP client interface.

This rule checks for the following calls:

  - `httplib.HTTPSConnection`
  - `http.client.HTTPSConnection`
  - `six.moves.http_client.HTTPSConnection`

## Further Reading

* [The Python Standard Library - HTTPSConnection](https://docs.python.org/2/library/httplib.html#httplib.HTTPSConnection)
* [The Python Standard Library - ssl - Security considerations](https://docs.python.org/2/library/ssl.html#ssl-security)
* [OpenStack - B309: httpsconnection](https://docs.openstack.org/developer/bandit/api/bandit.blacklists.html#b309-httpsconnection)
