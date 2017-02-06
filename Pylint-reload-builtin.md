Pattern: Reload builtin

Issue: -

## Description

Used when the reload built-in function is referenced (missing from Python 3). You can use instead imp.reload or importlib.reload. This message can't be emitted when using Python >= 3.0.