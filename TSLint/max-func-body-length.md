Pattern: Function is too long

Issue: -

## Description

Avoid long functions. The line count of a function body must not exceed the value configured within this rule's options.  

## Configuration

You can set up a general max function body length applied for every function/method/arrow function e.g. `[true, 30]` or set different
maximum length for every type:
```
[true, {
    "func-body-length": 10,
    "func-expression-body-length": 10,
    "arrow-body-length": 5,
    "method-body-length": 15,
    "ctor-body-length": 5
}]
```

To specify a function name whose parameters you can ignore for this
rule, pass a regular expression as a string(this can be useful for Mocha
users to ignore the `describe()` function). Since version 2.0.9, you can
also ignore single and multi-line comments from the total function
length:
```
[true, {
    "ignore-comments": true
}]
```

## Further Reading

* [TSLint - max-func-body-length](https://github.com/microsoft/tslint-microsoft-contrib/blob/master/README.md#supported-rules)