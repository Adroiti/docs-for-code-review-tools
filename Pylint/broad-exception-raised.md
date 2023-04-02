Pattern: Broad exception raised

Issue: -

## Description

Raising exceptions that are too generic force you to catch exceptions generically too. It will force you to use a naked `except Exception:` clause. You might then end up catching exceptions other than the ones you expect to catch. This can hide bugs or make it harder to debug programs when unrelated errors are hidden.

Example of **incorrect** code:

```python
def small_apple(apple, length):
    if len(apple) < length:
        raise Exception("Apple is too small!")  # [broad-exception-raised]
    print(f"{apple} is proper size.")
```

Example of **correct** code:

```python
def small_apple(apple, length):
    if len(apple) < length:
        raise ValueError("Apple is too small!")
    print(f"{apple} is proper size.")
```