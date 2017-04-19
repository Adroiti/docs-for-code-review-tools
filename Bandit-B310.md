Pattern: Use of urllib urlopen

Issue: -

## Description

Audit url open for permitted schemes. Allowing use of ‘file:’’ or custom
schemes is often unexpected.

This rule checks for the following calls:

  - urllib.urlopen
  - urllib.request.urlopen
  - urllib.urlretrieve
  - urllib.request.urlretrieve
  - urllib.URLopener
  - urllib.request.URLopener
  - urllib.FancyURLopener
  - urllib.request.FancyURLopener
  - urllib2.urlopen
  - urllib2.Request
  - six.moves.urllib.request.urlopen
  - six.moves.urllib.request .urlretrieve
  - six.moves.urllib.request .URLopener
  - six.moves.urllib.request .FancyURLopener

## Further Reading

* [OpenStack - B310: urllib_urlopen](https://docs.openstack.org/developer/bandit/api/bandit.blacklists.html#b310-urllib_urlopen)
