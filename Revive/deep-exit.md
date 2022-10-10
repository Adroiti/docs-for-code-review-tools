Pattern: Unexpected program exit

Issue: -

## Description

Packages exposing functions that can stop program execution by exiting are hard to reuse. This rule looks for program exits in functions other than `main()` or `init()`.

## Further Reading

* [Revive - deep-exit](https://revive.run/r#deep-exit)