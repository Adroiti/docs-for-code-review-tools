Pattern: Function modifies parameter

Issue: -

## Description

A function that modifies its parameters can be hard to understand. It can also be misleading if the arguments are passed by value by the caller.
This rule warns when a function modifies one or more of its parameters.

## Further Reading

* [Revive - modifies-parameter](https://revive.run/r#modifies-parameter)