Pattern: Binding to all interfaces

Issue: -

## Description

Binding to all network interfaces can potentially open up a service to traffic
on unintended interfaces, that may not be properly documented or secured. This
rule looks for a string pattern "0.0.0.0" that may indicate a hardcoded
binding to all network interfaces.

Example of **incorrect** code:

```python

>> Issue: Possible binding to all interfaces.
   Severity: Medium   Confidence: Medium
   Location: ./examples/binding.py:4
3   s = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
4   s.bind(('0.0.0.0', 31137))
5   s.bind(('192.168.0.1', 8080))

```

## Further Reading

  - __TODO__ : add best practice info on binding to all interfaces, and link here.
* [OpenStack - B104: hardcoded_bind_all_interfaces](https://docs.openstack.org/developer/bandit/plugins/hardcoded_bind_all_interfaces.html)
