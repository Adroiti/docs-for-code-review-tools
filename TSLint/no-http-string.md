Pattern: Use of HTTP string

Issue: -

## Description

Do not use strings that start with 'http:'. URL strings should start
with 'https:'. HTTP strings can be a security problem and indicator that
your software may suffer from cookie-stealing attacks. 

Since version 1.0, this rule takes a list of regular expressions as a parameter. Any
string matching that regular expression will be ignored. For example, to
allow HTTP connections to example.com and examples.com, configure your
rule like this: `"no-http-string": [true, "http://www.example.com/?.*", "http://www.examples.com/?.*"]`.

## Further Reading

* [TSLint - no-http-string](https://github.com/microsoft/tslint-microsoft-contrib/blob/master/README.md#supported-rules)