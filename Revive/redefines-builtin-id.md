Pattern: Redefining builtin name

Issue: -

## Description

Constant names like `false`, `true`, `nil`, function names like `append`, `make`, and basic type names like `bool`, and `byte` are not reserved words of the language; therefore the can be redefined.
Even if possible, redefining these built in names can lead to bugs very difficult to detect.

## Further Reading

* [Revive - redefines-builtin-id](https://revive.run/r#redefines-builtin-id)