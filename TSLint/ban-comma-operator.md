Pattern: Use of `,` operator

Issue: -

## Description

Bans the comma operator. It can be easily misunderstood or lead to unintended bugs.

For example, in `let x = (y = 1, z = 2);` x is equal to 2 - this may not be immediately obvious.

## Further Reading

* [TSLint - ban-comma-operator](https://palantir.github.io/tslint/rules/ban-comma-operator)