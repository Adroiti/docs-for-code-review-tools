Pattern: Insecure usage of temporary file/directory

Issue: -

## Description

Safely creating a temporary file or directory means following a number of
rules (see the references for more details). This rule looks for
strings starting with (configurable) commonly used temporary paths, for
example:

- `/tmp`
- `/var/tmp`
- `/dev/shm`
- `etc`


Example of **insecure** code:

```python
f = open('/tmp/abc', 'w')
f.write('def')
f.close()
```

Example of **secure** code:

```python
f = open('/abc/tmp', 'w')
f.write('def')
f.close()
```

## Further Reading

* [OpenStack - Create, use, and remove temporary files securely](https://security.openstack.org/guidelines/dg_using-temporary-files-securely.html)
* [OpenStack - B108: hardcoded_tmp_directory](https://docs.openstack.org/developer/bandit/plugins/hardcoded_tmp_directory.html)
