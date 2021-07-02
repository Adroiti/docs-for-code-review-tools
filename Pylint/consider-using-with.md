Pattern: Missing use of `with` block

Issue: -

## Description

Emitted if a resource-allocating assignment or call may be replaced by a `with` block. By using `with` the release of the allocated resources is ensured even in the case of an exception.
