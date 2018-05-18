Pattern: Starting a process with no shell

Issue: -

## Description

This rule looks for the spawning of a subprocess in a way that doesn't use a shell. Although this is
generally safe, it maybe useful for penetration testing work-flows to track where external system calls are used.


## Further Reading

* [The Python Standard Library - os.system](https://docs.python.org/2/library/os.html#os.system)
* [The Python Standard Library - subprocess - Frequently Used Arguments](https://docs.python.org/2/library/subprocess.html#frequently-used-arguments)
* [OpenStack - B606: start_process_with_no_shell](https://docs.openstack.org/developer/bandit/plugins/start_process_with_no_shell.html)
