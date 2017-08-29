Pattern: Use of explicit arguments for `make_pair`

Issue: -

## Description

G++ 4.6 in C++11 mode fails badly if make_pair's template arguments are specified explicitly, and such use isn't intended in any case.

For C++11-compatibility, omit template arguments from `make_pair` OR use pair directly OR if appropriate, construct a pair directly.
