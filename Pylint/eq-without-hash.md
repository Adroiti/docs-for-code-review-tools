Pattern: Use of `__eq__` without `__hash__`

Issue: -

## Description

Used when a class implements `__eq__` but not `__hash__`. In _Python 2_, objects get `object.__hash__` as the default implementation, in _Python 3_ objects get `None` as their default `__hash__` implementation if they also implement `__eq__`.
