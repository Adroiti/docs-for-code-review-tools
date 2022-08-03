Pattern: Unnecessary `!!`

Issue: -

## Description

Reports unnecessary not-null operator usage (`!!`) that can be removed by the user.
Example of **incorrect** code:

```kotlinval a = 1
val b = a!!```

Example of **correct** code:

```kotlinval a = 1
val b = a```

## Further Reading

* [Detekt - UnnecessaryNotNullOperator](https://detekt.dev/docs/rules/potential-bugs/#unnecessarynotnulloperator)