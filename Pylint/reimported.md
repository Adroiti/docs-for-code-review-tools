Pattern: Module imported multiple times

Issue: -

## Description

Used when a module is re-imported multiple times. This may lead to confusion by readers and increased code size.


Example of **incorrect** code:

```python
from time import sleep, sleep
```

Example of **correct** code:

```python
from time import sleep
```
