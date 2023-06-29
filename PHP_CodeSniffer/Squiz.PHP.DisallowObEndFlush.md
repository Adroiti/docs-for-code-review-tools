Pattern: Use of `ob_end_flush()`

Issue: -

## Description

Use of `ob_end_flush()` is not allowed; use `ob_get_contents()` and `ob_end_clean()` instead.
