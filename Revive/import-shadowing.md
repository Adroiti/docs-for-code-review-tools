Pattern: Use of import shadowing

Issue: -

## Description

In GO it is possible to declare identifiers (packages, structs,
interfaces, parameters, receivers, variables, constants...) that conflict with the
name of an imported package. This rule spots identifiers that shadow an import.

## Further Reading

* [Revive - import-shadowing](https://revive.run/r#import-shadowing)