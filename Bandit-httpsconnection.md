Pattern: Use of httpsconnection

Issue: -

## Description

Use of HTTPSConnection on older versions of Python prior to 2.7.9 and 3.4.3 do
not provide security, see <https://wiki.openstack.org/wiki/OSSN/OSSN-0033>

This rule checks for the following calls:

  - httplib.HTTPSConnection
  - http.client.HTTPSConnection
  - six.moves.http_client .HTTPSConnection

## Further Reading

* [OpenStack - B309: httpsconnection](https://docs.openstack.org/developer/bandit/api/bandit.blacklists.html#b309-httpsconnection)
