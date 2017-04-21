Pattern: No certificate validation for `Requests` method

Issue: -

## Description

This rule enforces to always verify SSL certificate for `Requests` methods. Certificates are validated by default which is the desired behavior. 

Encryption in general is typically critical to the security of many
applications. Using TLS can greatly increase security by guaranteeing the
identity of the party you are communicating with. This is accomplished by one
or both parties presenting trusted certificates during the connection
initialization phase of TLS.


Example of **incorrect** code:

```python
import requests

requests.get('https://www.openstack.org/', verify=False)
```

Example of **correct** code:

```python
import requests

requests.get('https://www.openstack.org/', verify=True)
```

It is important to note that modules such as httplib within the Python standard library did not verify certificate chains until it was fixed in 2.7.9 release.

## Further Reading

* [Requests - SSL Cert Verification](http://docs.python-requests.org/en/master/user/advanced/#ssl-cert-verification)
* [OpenStack - Validate certificates on HTTPS connections to avoid man-in-the-middle attacks](https://security.openstack.org/guidelines/dg_validate-certificates.html)
* [OpenStack - B501: request_with_no_cert_validation](https://docs.openstack.org/developer/bandit/plugins/request_with_no_cert_validation.html)
