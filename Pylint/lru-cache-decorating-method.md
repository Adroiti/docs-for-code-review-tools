Pattern: Use of `lru_cache` method

Issue: -

## Description

By decorating a method with `lru_cache` the `self` argument will be linked to the `lru_cache` function and therefore is never garbage collected. Unless your instance will never need to be garbage collected (singleton) it is recommended to refactor code to avoid this pattern or add a maxsize to the cache.
