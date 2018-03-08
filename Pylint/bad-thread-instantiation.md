Pattern: Bad thread instantiation

Issue: -

## Description

Emitted when the `threading.Thread` class does not receive the target argument, but receives just one argument, which is by default the group parameter.

Example of **incorrect** code:

```python
import threading
threading.Thread(lambda: print(1)) #this is the group parameter
```

Example of **correct** code:

```python
threading.Thread(target=worker)
```