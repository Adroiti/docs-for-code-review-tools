Pattern: Use of insecure `random` module

Issue: -

## Description

The pseudo-random generators of `random` module should not be used for security purposes. Use `os.urandom()` or `SystemRandom` if you require a cryptographically secure pseudo-random number generator.

This rule checks for the following calls:

  - `random.random`
  - `random.randrange`
  - `random.randint`
  - `random.choice`
  - `random.uniform`
  - `random.triangular`


Example of **insecure** code:

```python
import random
import os

number = random.random()
```

Example of **secure** code:

```python
import random
import os

number = random.SystemRandom()
```
  
## Further Reading

* [The Python Standard Library - random](https://docs.python.org/2/library/random.html)
* [OpenStack - B311: random](https://docs.openstack.org/developer/bandit/api/bandit.blacklists.html#b311-random)
