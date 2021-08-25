Pattern: Use of `dict()` instead of `{}`

Issue: -

## Description

Emitted when using `dict()` to create an empty dictionary instead of the literal `{}`. The literal is faster as it avoids an additional function call.
