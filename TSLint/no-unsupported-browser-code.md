Pattern: Unsupported browser code

Issue: -

## Description

Avoid writing browser-specific code for unsupported browser versions.
Browser versions are specified in the rule configuration options, eg:
`[true, [ "IE 11", "Firefox > 40", "Chrome >= 45" ] ]`. Browser-specific
blocks of code can then be designated with a single-line comment, like
so: `// Browser specific: IE 10`, or with a jsdoc like this:
`@browserspecific chrome 40`.

## Further Reading

* [TSLint - no-unsupported-browser-code](https://github.com/microsoft/tslint-microsoft-contrib/blob/master/README.md#supported-rules)