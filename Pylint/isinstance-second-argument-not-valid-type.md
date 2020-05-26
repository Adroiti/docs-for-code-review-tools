Pattern: 2nd argument of `isinstance` is not a type

Issue: -

## Description

Emitted when the second argument of an `isinstance` call is not a type.

Example of **incorrect** code:

```python
isinstance({a:1}, hash) # [isinstance-second-argument-not-valid-type]
```

Example of **correct** code:

```python
isinstance(-999, int)
```