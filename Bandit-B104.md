Pattern: Binding to all interfaces

Issue: -

## Description

Binding to all network interfaces can potentially open up a service to traffic
on unintended interfaces, that may not be properly documented or secured. This
rule looks for a string pattern "0.0.0.0" that may indicate a hardcoded
binding to all network interfaces.


Example of **incorrect** code:

```python
s.bind(('0.0.0.0', 8080))
```

Example of **correct** code:

```python
s.bind(('192.168.0.1', 8080))
```

## Further Reading

* [OpenStack - B104: hardcoded_bind_all_interfaces](https://docs.openstack.org/developer/bandit/plugins/hardcoded_bind_all_interfaces.html)
