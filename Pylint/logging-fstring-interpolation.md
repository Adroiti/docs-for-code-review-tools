Pattern: Use of `f"..."` in logging function

Issue: -

## Description

Used when a logging statement has a call form of `logging.method(f"..."))`. Such calls should use `%` formatting instead, but leave interpolation to the logging function by passing the parameters as arguments.
