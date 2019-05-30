Pattern: Use of non-literal `require()`

Issue: -

## Description

Detects `require()` function calls for something that is not a string
literal. For security reasons, it may be best to only `require()` string
literals. Otherwise, it may be possible for an attacker to somehow
change the value and download arbitrary Javascript into your page.

## Further Reading

* [TSLint - non-literal-require](https://github.com/microsoft/tslint-microsoft-contrib/blob/master/README.md#supported-rules)