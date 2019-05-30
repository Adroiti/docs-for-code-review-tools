Pattern: Unnecessary field initialization

Issue: -

## Description

Do not unnecessarily initialize the fields of a class to values they
already have. For example, there is no need to explicitly set a field to
`undefined` in the field's initialization or in the class' constructor.
Also, if a field is initialized to a constant value (null, a string, a
boolean, or some number) then there is no need to reassign the field to
this value within the class constructor.

## Further Reading

* [TSLint - no-unnecessary-field-initialization](https://github.com/microsoft/tslint-microsoft-contrib/blob/master/README.md#supported-rules)