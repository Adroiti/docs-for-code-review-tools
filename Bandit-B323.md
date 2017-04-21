Pattern: Use of `ssl._create_unverified_context()`

Issue: -

## Description

By default, Python will create a secure, verified ssl context for use in such
classes as `HTTPSConnection`. However, it still allows using an insecure context
via the `_create_unverified_context` that reverts to the previous behavior that
does not validate certificates or perform hostname checks.


Example of **insecure** code:

```python
import ssl

context = ssl._create_unverified_context()
```

Example of **secure** code:

```python
import ssl

context = ssl.create_default_context()
```

## Further Reading

* [OpenStack - B323: unverified_context](https://docs.openstack.org/developer/bandit/api/bandit.blacklists.html#b323-unverified-context)
