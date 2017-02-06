Pattern: Using cmp argument

Issue: -

## Description

Using the cmp argument for list.sort or the sorted builtin should be avoided, since it was removed in Python 3. Using either `key` or `functools.cmp_to_key` should be preferred. This message can't be emitted when using Python >= 3.0.