Pattern: Constant expression in condition

Issue: -

## Description

Do not use constant expressions in conditions. Similar to the [ESLint no-constant-condition](https://eslint.org/docs/rules/no-constant-condition) rule. 

## Configuration

Since version 2.0.14, this rule accepts a parameter called `checkLoops` which defaults to true. If set to false then loops are not checked for conditionals. For example, disable loop checking with:
```
[true, {
    'checkLoops': false
}]
```

## Further Reading

* [TSLint - no-constant-condition](https://github.com/microsoft/tslint-microsoft-contrib/blob/master/README.md#supported-rules)