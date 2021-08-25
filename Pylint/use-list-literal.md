Pattern: Use of `list()` instead of `[]`

Issue: -

## Description

Emitted when using `list()` to create an empty list instead of the literal `[]`. The literal is faster as it avoids an additional function call.
