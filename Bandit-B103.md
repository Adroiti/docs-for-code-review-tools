Pattern: Setting permissive file permissions

Issue: -

## Description


This rule looks for the use of `chmod` and will alert when it is used
to set particularly permissive control flags. Discretion should be used when granting write access to files such as configuration files to prevent vulnerabilities including denial of service and remote code execution.

POSIX based operating systems utilize a permissions model to protect access to
parts of the file system. This model supports three roles - `owner`, `group` and
`world`. Each role may have a combination of `read`, `write` or `execute` flags
sets. Python provides `chmod` to manipulate POSIX style permissions.


Example of **incorrect** code:

```python
os.chmod('/etc/passwd', 07)
```

Example of **correct** code:

```python
os.chmod('/etc/passwd', 0664)
```

## Further Reading

* [OpenStack - Apply Restrictive File Permissions](https://security.openstack.org/guidelines/dg_apply-restrictive-file-permissions.html)
* [OpenStack - B103: set_bad_file_permissions](https://docs.openstack.org/developer/bandit/plugins/set_bad_file_permissions.html)
