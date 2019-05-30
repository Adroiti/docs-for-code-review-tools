Pattern: Unnecessary override

Issue: -

## Description

Do not write a method that only calls `super()` on the parent method with
the same arguments. You can safely remove methods like this and
Javascript will correctly dispatch the method to the parent object.

## Further Reading

* [TSLint - no-unnecessary-override](https://github.com/microsoft/tslint-microsoft-contrib/blob/master/README.md#supported-rules)