Pattern: Missing use of `maxsplit`

Issue: -

## Description

Emitted when accessing only the first or last element of `str.split()`. The first and last element can be accessed by using `str.split(sep, maxsplit=1)[0]` or `str.rsplit(sep, maxsplit=1)[-1]` instead.
