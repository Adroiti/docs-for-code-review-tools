Pattern: Use of insecure SSL/TLS as method parameter value

Issue: -

## Description

Several highly publicized exploitable flaws have been discovered in all
versions of SSL and early versions of TLS. It is strongly recommended that use
of the following known broken protocol versions be avoided:

  - SSL v2
  - SSL v3
  - TLS v1
  - TLS v1.1
  
This rule scans for Python methods with default parameter values that specify the use of broken SSL/TLS protocol versions. Currently,
detection supports methods using Python's native SSL/TLS support and the `pyOpenSSL` module.


Example of **incorrect** code:

```python
import ssl
from pyOpenSSL import SSL

def open_ssl_socket(version=SSL.TLSv1_METHOD):
    pass
```

Example of **correct** code:

```python
import ssl
from pyOpenSSL import SSL

def open_ssl_socket(version=SSL.TLSv1_2_METHOD):
    pass
```

## Further Reading

* [The Python Standard Library - ssl - Security considerations](https://docs.python.org/2/library/ssl.html#security-considerations)
* [The Heartbleed Bug](http://heartbleed.com/)
* [OpenStack - B503: ssl_with_bad_defaults](https://docs.openstack.org/developer/bandit/plugins/ssl_with_bad_defaults.html)
