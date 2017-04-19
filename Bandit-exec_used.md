Pattern: The use of exec

Issue: -

## Description

This rule checks for the use of Python's exec method or keyword. The
Python docs succinctly describe why the use of exec is risky.

Example of **incorrect** code:

```python

>> Issue: Use of exec detected.
   Severity: Medium   Confidence: High
   Location: ./examples/exec-py2.py:2
1 exec("do evil")
2 exec "do evil"

```

## Further Reading

  - <https://docs.python.org/2.0/ref/exec.html>
  - TODO: add info on exec and similar to sec best practice and link here
* [OpenStack - B102: exec_used](https://docs.openstack.org/developer/bandit/plugins/exec_used.html)
