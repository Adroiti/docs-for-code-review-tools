Pattern: Function call with `shell=True`

Issue: -

## Description

This rule interrogates method calls for the presence of a keyword parameter _shell_ equalling true. It
is related to detection of shell injection issues and is intended to catch custom wrappers to vulnerable methods that may have been created.


Example of **incorrect** code:

```python
import subprocess
from subprocess import Popen as pop

pop('/bin/gcc --version', shell=True)
```

Example of **correct** code:

```python
import subprocess
from subprocess import Popen as pop

pop('/bin/gcc --version', shell=False)
```

## Further Reading

* [The Python Standard Library - subprocess - Frequently Used Arguments](https://docs.python.org/2/library/subprocess.html#frequently-used-arguments)
* [OpenStack - B604: any_other_function_with_shell_equals_true](https://docs.openstack.org/developer/bandit/plugins/any_other_function_with_shell_equals_true.html)
