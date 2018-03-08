Pattern: Use of `copy.copy(os.environ)`

Issue: -

## Description

`os.environ` is not a dictionary but a proxy object, so shallow copy has still effects on original object. Use `os.environ.copy()` instead.


Example of **incorrect** code:

```python
import copy
import os

wrong_env_copy = copy.copy(os.environ)  # will emit pylint warning
wrong_env_copy['ENV_VAR'] = 'new_value'  # changes os.environ
assert os.environ['ENV_VAR'] == 'new_value'
```

Example of **correct** code:

```python
import copy
import os

good_env_copy = dict(os.environ)
good_env_copy['ENV_VAR'] = 'different_value'  # doesn't change os.environ
assert os.environ['ENV_VAR'] == 'new_value'
```

## Further Reading

* [Python - Issue15373](https://bugs.python.org/issue15373)
