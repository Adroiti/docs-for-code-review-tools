Pattern: Use of non-literal `fs` path

Issue: -

## Description

Detects `fs` function calls with a non literal filepath. For security
reasons, it may be best to only pass string literals as filesystem
paths. Otherwise, it may be possible for an attacker to read and write
arbitrary files on your system through path traversal attacks.

## Further Reading

* [TSLint - non-literal-fs-path](https://github.com/microsoft/tslint-microsoft-contrib/blob/master/README.md#supported-rules)