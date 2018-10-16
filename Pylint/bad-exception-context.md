Pattern: Invalid exception context for `raise ... from ...`

Issue: -

## Description

Emitted when using the syntax `raise ... from ...`, where the exception context is not an exception, nor `None`.
