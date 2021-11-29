Pattern: Unnecessary `with` lock

Issue: -

## Description

Used when a new lock instance is created by using with statement which has no effect. Instead, an existing instance should be used to acquire lock.


Example of **incorrect** code:

```python
import threading
from threading import Lock, RLock, Condition, Semaphore, BoundedSemaphore


with threading.Lock():  # [useless-with-lock]
    ...
```

Example of **correct** code:

```python
import threading
from threading import Lock, RLock, Condition, Semaphore, BoundedSemaphore


lock = threading.Lock()
with lock:  # this is ok
    ...
```