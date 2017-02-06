Pattern: Unused format string argument

Issue: -

## Description

Used when a PEP 3101 format string that uses named fields is used with an argument that is not required by the format string. This message can't be emitted when using Python < 2.7.