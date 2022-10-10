Pattern: `sync.WaitGroup` passed by value

Issue: -

## Description

Function parameters that are passed by value, are in fact a copy of the original argument. Passing a copy of a `sync.WaitGroup` is usually not what the developer wants to do.
This rule warns when a `sync.WaitGroup` expected as a by-value parameter in a function or method.

## Further Reading

* [Revive - waitgroup-by-value](https://revive.run/r#waitgroup-by-value)