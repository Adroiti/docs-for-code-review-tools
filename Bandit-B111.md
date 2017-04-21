Pattern: Use of rootwrap running as root

Issue: -

## Description

Running commands as root dramatically increase their potential risk. Running
commands with restricted user privileges provides defense in depth against
command injection attacks, or developer and configuration error. This rule checks for specific methods being called with a keyword parameter `run_as_root` set to `True`, a common OpenStack idiom:

- `ceilometer.utils.execute`
- `cinder.utils.execute`
- `neutron.agent.linux.utils.execute`
- `nova.utils.execute`
- `nova.utils.trycmd`


Example of **insecure** code:

```python
ceilometer_utils.execute('gcc --version', run_as_root=True)
```

Example of **secure** code:

```python
ceilometer_utils.execute('gcc --version', run_as_root=False)
```

## Further Reading

* [OpenStack - Using Rootwrap in OpenStack](https://security.openstack.org/guidelines/dg_rootwrap-recommendations-and-plans.html)
* [OpenStack - Use oslo rootwrap securely](https://security.openstack.org/guidelines/dg_use-oslo-rootwrap-securely.html)
* [OpenStack - B111: execute_with_run_as_root_equals_true](https://docs.openstack.org/developer/bandit/plugins/execute_with_run_as_root_equals_true.html)
