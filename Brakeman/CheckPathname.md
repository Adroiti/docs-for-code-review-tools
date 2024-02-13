Pattern: Unexpected `Pathname` behavior

Issue: -

## Description

Absolute paths in `Pathname#join` cause the entire path to be relative to the absolute path, ignoring any prior values.