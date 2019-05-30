Pattern: Invalid function name

Issue: -

## Description

Applies a naming convention to function names and method names. You can
configure the naming convention by passing parameters. 

## Configuration

The default values are:

```json
[true, {
    "method-regex": "^[a-z][\\w\\d]+$",
    "private-method-regex": "^[a-z][\\w\\d]+$",
    "protected-method-regex": "^[a-z][\\w\\d]+$",
    "static-method-regex": "^[A-Z_\\d]+$",
    "function-regex": "^[a-z][\\w\\d]+$"
}]
```

## Further Reading

* [TSLint - function-name](https://github.com/microsoft/tslint-microsoft-contrib/blob/master/README.md#supported-rules)