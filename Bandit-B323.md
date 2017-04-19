Pattern: Use of unverified context

Issue: -

## Description

By default, Python will create a secure, verified ssl context for use in such
classes as HTTPSConnection. However, it still allows using an insecure context
via the _create_unverified_context that reverts to the previous behavior that
does not validate certificates or perform hostname checks.

This rule checks for the following calls:

B322

  - ssl._create_
`bandit.blacklists.calls.``gen_blacklist`()

    

Generate a list of items to blacklist.

Methods of this type, “bandit.blacklist” plugins, are used to build a list of
items that bandit’s built in blacklisting tests will use to trigger issues.
They replace the older blacklist* test plugins and allow blacklisted items to
have a unique bandit ID for filtering and profile usage.

Returns:

a dictionary mapping node types to a list of blacklist data

## Further Reading

* [OpenStack - B323: unverified_context](https://docs.openstack.org/developer/bandit/api/bandit.blacklists.html#b323-unverified-context)
