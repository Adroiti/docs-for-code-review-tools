Pattern: Missing directory for `.h` file `include`

Issue: -

## Description

`include` should use the new style `foo/bar.h` instead of just `bar.h`. Only do this check if the included header follows google naming
conventions. If not, assume that it's a 3rd party API that requires special include conventions.

We also make an exception for Lua headers, which follow google naming convention but not the include convention.
