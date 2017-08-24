Pattern: Binary op exception

Issue: -

## Description

Used when the exception to catch is of the form `except A or B:`. If intending to catch multiple, rewrite as `except (A, B):`.