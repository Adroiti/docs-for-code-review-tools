Pattern: Import is related to `httpoxy` vulnerabilities

Issue: -

## Description

`httpoxy` is a set of vulnerabilities that affect application code running in
CGI, or CGI-like environments. The use of CGI for web applications should be
avoided to prevent this class of attack.

This rule checks for the following imports:

  - `wsgiref.handlers.CGIHandler`
  - `twisted.web.twcgi.CGIScript`

## Further Reading

* [httpoxy](https://httpoxy.org)
* [OpenStack - B412: import_httpoxy](https://docs.openstack.org/developer/bandit/api/bandit.blacklists.html#b412-import-httpoxy)
