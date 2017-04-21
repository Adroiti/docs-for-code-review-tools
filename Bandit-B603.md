Pattern: Use of `subprocess` without `shell=True`

Issue: -

## Description

This test looks for the spawning of a `subprocess` without the use of a command shell. This type of
`subprocess` invocation is not vulnerable to shell injection attacks, but care should still be taken to ensure validity of input.

## Further Reading

* [The Python Standard Library - subprocess - Frequently Used Arguments](https://docs.python.org/2/library/subprocess.html#frequently-used-arguments)
* [OpenStack - B603: subprocess_without_shell_equals_true](https://docs.openstack.org/developer/bandit/plugins/subprocess_without_shell_equals_true.html)
