Pattern: Use of `assert` on string literal

Issue: -

## Description

Used when an `assert` statement has a string literal as its first argument, which will cause the assert to always pass.

Example of **incorrect** code:

```python
assert "There is an AssertionError" # [assert-on-string-literal]
```

Example of **correct** code:

```python
assert [foo, bar], "No AssertionError"
```