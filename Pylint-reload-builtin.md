Pattern: Reload built-in

Issue: -

## Description

Used when the `reload()` built-in function is referenced (missing from Python 3). You can use `imp.reload()` or `importlib.reload()` instead. This message can't be emitted when using Python >= 3.0.
