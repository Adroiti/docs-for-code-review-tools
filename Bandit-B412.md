Pattern: Use of import httpoxy

Issue: -

## Description

httpoxy is a set of vulnerabilities that affect application code running in
CGI, or CGI-like environments. The use of CGI for web applications should be
avoided to prevent this class of attack. More details are available at
<https://httpoxy.org/>.

This rule checks for the following calls:

  - wsgiref.handlers.CGIHandler
  - twisted.web.twcgi.CGIScript

`bandit.blacklists.imports.``gen_blacklist`()

    

Generate a list of items to blacklist.

Methods of this type, “bandit.blacklist” plugins, are used to build a list of
items that bandit’s built in blacklisting tests will use to trigger issues.
They replace the older blacklist* test plugins and allow blacklisted items to
have a unique bandit ID for filtering and profile usage.

Returns:

a dictionary mapping node types to a list of blacklist data

## Further Reading

* [OpenStack - B412: import_httpoxy](https://docs.openstack.org/developer/bandit/api/bandit.blacklists.html#b412-import-httpoxy)
