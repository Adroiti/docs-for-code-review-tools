Pattern: Use of function that creates breakpoint

Issue: -

## Description

Calls to `breakpoint()`, `sys.breakpointhook()` and `pdb.set_trace()` should be removed from code that is not actively being debugged.
