Pattern: Missing `sandbox` for React iframe

Issue: -

## Description

React iframes must specify a `sandbox` attribute. If specified as an empty
string, this attribute enables extra restrictions on the content that
can appear in the inline frame. The value of the attribute can either be
an empty string (all the restrictions are applied), or a space-separated
list of tokens that lift particular restrictions. You many not use both
allow-scripts and allow-same-origin at the same time, as that allows the
embedded document to programmatically remove the `sandbox` attribute in
some scenarios.

## Further Reading

* [TSLint - react-iframe-missing-sandbox](https://github.com/microsoft/tslint-microsoft-contrib/blob/master/README.md#supported-rules)