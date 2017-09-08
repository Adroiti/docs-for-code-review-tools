Pattern: Assignment in conditional

Issue: -

## Description

Disallows any type of assignment in conditionals.  
  
Rationale: Assignments in conditionals are often typos: for example `if (var1 = var2)` instead of `if (var1 == var2)`. They also can be an indicator of overly clever code which decreases maintainability.

## Further Reading

* [TSLint - no-conditional-assignment](https://palantir.github.io/tslint/rules/no-conditional-assignment)