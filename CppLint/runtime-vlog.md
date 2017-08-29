Pattern: Misused `VLOG()`

Issue: -

## Description

Checks that `VLOG()` is only used for defining a logging level. For example, `VLOG(2)` is correct. `VLOG(INFO)`, `VLOG(WARNING)`, `VLOG(ERROR)`, and
  `VLOG(FATAL)` are not.
