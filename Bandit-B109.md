Pattern: A password based config option not marked secret

Issue: -

## Description

Passwords are sensitive and must be protected appropriately. In OpenStack Oslo
there is an option to mark options "secret" which will ensure that they are
not logged. This plugin detects usages of oslo configuration functions that
appear to deal with strings ending in 'password' and flag usages where they
have not been marked secret.


Example of **incorrect** code:

```python
cfg.StrOpt('admin_password', help="User's password")
```

Example of **correct** code:

```python
cfg.StrOpt('admin_password', secret=True, help="User's password")
```

## Further Reading

* [OpenStack - Protect sensitive data in config files from disclosure](https://security.openstack.org/guidelines/dg_protect-sensitive-data-in-files.html)
* [OpenStack - B109: password_config_option_not_marked_secret](https://docs.openstack.org/developer/bandit/plugins/password_config_option_not_marked_secret.html)
