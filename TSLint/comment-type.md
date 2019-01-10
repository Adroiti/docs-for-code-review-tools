Pattern: Malformed comment

Issue: -

## Description

Allows a limited set of comment types.

One or more of the following mutually exclusive comment types may be provided:

* `singleline`: Comments starting with `//`
* `multiline`: Comments between `/*` and `*/` but are not doc comments
* `doc`: Multiline comments that start with `/**`
* `directive`: Triple-slash directives that are singleline comments starting with `///`

## Further Reading

* [TSLint - comment-type](https://palantir.github.io/tslint/rules/comment-type)