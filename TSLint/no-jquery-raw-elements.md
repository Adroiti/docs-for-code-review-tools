Pattern: Use of JQuery raw element

Issue: -

## Description

Do not create HTML elements using JQuery and string concatenation. It is
error prone and can hide subtle defects. Instead use the JQuery element API.

## Further Reading

* [TSLint - no-jquery-raw-elements](https://github.com/microsoft/tslint-microsoft-contrib/blob/master/README.md#supported-rules)