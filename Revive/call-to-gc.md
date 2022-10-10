Pattern: Explicit call to garbage collector

Issue: -

## Description

Explicitly invoking the garbage collector is, except for specific uses in benchmarking, very dubious.

The garbage collector can be configured through environment variables as described [here](https://golang.org/pkg/runtime/).

## Further Reading

* [Revive - call-to-gc](https://revive.run/r#call-to-gc)