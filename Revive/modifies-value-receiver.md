Pattern: Method modifies value receiver

Issue: -

## Description

A method that modifies its receiver value can have undesired behavior. The modification can be also the root of a bug because the actual value receiver could be a copy of that used at the calling site.
This rule warns when a method modifies its receiver.

## Further Reading

* [Revive - modifies-value-receiver](https://revive.run/r#modifies-value-receiver)