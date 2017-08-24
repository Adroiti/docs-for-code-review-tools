Pattern: Use of insecure SSL/TLS as default method value

Issue: -

## Description

Several highly publicized exploitable flaws have been discovered in all
versions of SSL and early versions of TLS. It is strongly recommended that use
of the following known broken protocol versions be avoided:

  - SSL v2
  - SSL v3
  - TLS v1
  - TLS v1.1

This rule scans for specific methods in Python's native SSL/TLS support and the `pyOpenSSL` module that configure the version of SSL/TLS
protocol to use. These methods are known to provide default value that maximize compatibility, but permit use of the aforementioned broken protocol versions.


Example of **insecure** code:

```python
import ssl
from pyOpenSSL import SSL

ssl.wrap_socket()
```

Example of **secure** code:

```python
import ssl
from pyOpenSSL import SSL

ssl.wrap_socket(ssl_version=ssl.PROTOCOL_TLSv1_2)
```

When using SSLv23 it is important to also provide flags to explicitly exclude bad versions of SSL/TLS from the protocol versions considered. Both the Python native and `pyOpenSSL` modules provide the `OP_NO_SSLv2` and `OP_NO_SSLv3` flags for this purpose.

## Further Reading

* [The Python Standard Library - ssl - Security considerations](https://docs.python.org/2/library/ssl.html#security-considerations)
* [The Heartbleed Bug](http://heartbleed.com)
* [OpenStack - B504: ssl_with_no_version](https://docs.openstack.org/developer/bandit/plugins/ssl_with_no_version.html)
