Pattern: Missing use `./` URL prefix

Issue: -

## Description

The `./` prefix is standard syntax for relative URLs; don’t depend on Angular’s current ability to do without that prefix. A component relative URL requires no change when you move the component files, as long as the files stay together.

## Further Reading

* [TSLint - relative-url-prefix](http://codelyzer.com/rules/relative-url-prefix/)