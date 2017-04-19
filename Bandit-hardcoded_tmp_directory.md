Pattern: Insecure usage of tmp file/directory

Issue: -

## Description

Safely creating a temporary file or directory means following a number of
rules (see the references for more details). This rule looks for
strings starting with (configurable) commonly used temporary paths, for
example:

- /tmp

- /var/tmp

- /dev/shm

- etc

**Config Options:**

This test plugin takes a similarly named config block,
hardcoded_tmp_directory. The config block provides a Python list, tmp_dirs,
that lists string fragments indicating possible temporary file paths. Any
string starting with one of these fragments will report a MEDIUM confidence
issue.

hardcoded_tmp_directory:
tmp_dirs: ['/tmp', '/var/tmp', '/dev/shm']

Example of **incorrect** code:

```python

```

## Further Reading

  - <https://security.openstack.org/guidelines/dg_using-temporary-files-securely.html>
* [OpenStack - B108: hardcoded_tmp_directory](https://docs.openstack.org/developer/bandit/plugins/hardcoded_tmp_directory.html)
