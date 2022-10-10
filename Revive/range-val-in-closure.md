Pattern: Use of range value in closure

Issue: -

## Description

Range variables in a loop are reused at each iteration; therefore a goroutine created in a loop will point to the range variable with from the upper scope. This way, the goroutine could use the variable with an undesired value.
This rule warns when a range value (or index) is used inside a closure.

## Further Reading

* [Revive - range-val-in-closure](https://revive.run/r#range-val-in-closure)