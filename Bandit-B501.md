Pattern: Missing certificate validation

Issue: -

## Description

Encryption in general is typically critical to the security of many
applications. Using TLS can greatly increase security by guaranteeing the
identity of the party you are communicating with. This is accomplished by one
or both parties presenting trusted certificates during the connection
initialization phase of TLS.

When request methods are used certificates are validated automatically which
is the desired behavior. If certificate validation is explicitly turned off
Bandit will return a HIGH severity error.

Example of **incorrect** code:

```python

>> Issue: [request_with_no_cert_validation] Requests call with verify=False
disabling SSL certificate checks, security issue.
   Severity: High   Confidence: High
   Location: examples/requests-ssl-verify-disabled.py:4
3   requests.get('https://gmail.com', verify=True)
4   requests.get('https://gmail.com', verify=False)
5   requests.post('https://gmail.com', verify=True)

```

## Further Reading

  - <https://security.openstack.org/guidelines/dg_move-data-securely.html>
  - <https://security.openstack.org/guidelines/dg_validate-certificates.html>
* [OpenStack - B501: request_with_no_cert_validation](https://docs.openstack.org/developer/bandit/plugins/request_with_no_cert_validation.html)
