Pattern: Indexing exception

Issue: -

## Description

Indexing exceptions will not work on Python 3. Use `exception.args[index]` instead. This message can't be emitted when using Python >= 3.0.