Pattern: Use of `lru_cache` method

Issue: -

## Description

By decorating a method with `lru_cache` the `self` argument will be linked to the `lru_cache` function and therefore is never garbage collected. Unless your instance will never need to be garbage collected (singleton) it is recommended to refactor code to avoid this pattern or add a maxsize to the cache.


Example of **incorrect** code:

```python
import functools

class Fibonnaci:
    @functools.lru_cache(maxsize=None)  # [method-cache-max-size-none]
    def fibonacci(self, n):
        if n in {0, 1}:
            return n
        return self.fibonacci(n - 1) + self.fibonacci(n - 2)
```

Example of **correct** code:

```python
import functools

@functools.cache
def cached_fibonacci(n):
    if n in {0, 1}:
        return n
    return cached_fibonacci(n - 1) + cached_fibonacci(n - 2)


class Fibonnaci:
    def fibonacci(self, n):
        return cached_fibonacci(n)

```