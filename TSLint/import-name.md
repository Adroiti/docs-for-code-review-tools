Pattern: Mismatched import name

Issue: -

## Description

The name of the imported module must match the name of the thing being
imported. For special characters (`-`, `.`, `_`) remove them and make
the following character uppercase. 

For example, it is valid to name imported modules the same as the module name:
`import Service = require('x/y/z/Service')` and
`import Service from 'x/y/z/Service'`. But it is invalid to change the
name being imported, such as:
`import MyCoolService = require('x/y/z/Service')` and
`import MyCoolService from 'x/y/z/Service'`. When containing special
characters such as `import $$ from 'my-awesome_library';` the
corresponding configuration would look like
`'import-name': [true, { 'myAwesomeLibrary': '$$' }]`. 

## Configuration

Since version 2.0.9 it is possible to configure this rule with a list of exceptions.
For example, to allow `underscore` to be imported as `_`, add this
configuration: `'import-name': [ true, { 'underscore': '_' }]`

## Further Reading

* [TSLint - import-name](https://github.com/microsoft/tslint-microsoft-contrib/blob/master/README.md#supported-rules)