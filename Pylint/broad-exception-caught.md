Pattern: Broad exception caught

Issue: -

## Description

If you use a naked `except Exception:` clause, you might end up catching exceptions other than the ones you expect to catch. This can hide bugs or make it harder to debug programs when unrelated errors are hidden.

Example of **incorrect** code:

```python
try:
    import platform_specific_module
except Exception:  # [broad-exception-caught]
    platform_specific_module = None
```

Example of **correct** code:

```python
try:
    import platform_specific_module
except ImportError:
    platform_specific_module = None
```