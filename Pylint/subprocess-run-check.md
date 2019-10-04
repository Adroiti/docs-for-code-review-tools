Pattern: Missing use of `check` for `subprocess.run`

Issue: -

## Description

`subprocess.run` uses a default of `check=False`, which means that a nonzero exit code will be ignored by default, instead of raising an exception.

This rule forces to set `check` keyword to make clear what the error-handling behavior is.

Example of **incorrect** code:

```python
import subprocess

cp = subprocess.run(["ls -lha"])
```

Example of **correct** code:

```python
import subprocess

cp = subprocess.run(["ls -lha"],check=True)
```