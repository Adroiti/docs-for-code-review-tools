Pattern: Eval used

Issue: -

## Description

Used when you use the `eval()` function, to discourage its usage. Consider using `ast.literal_eval()` for safely evaluating strings containing Python expressions from untrusted sources.