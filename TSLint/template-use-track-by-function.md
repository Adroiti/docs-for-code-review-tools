Pattern: Missing use of `trackBy`

Issue: -

## Description

The use of `trackBy` is considered a good practice.

To avoid expensive operations, you can customize the default tracking algorithm by supplying the `trackBy` option to `NgForOf`. `trackBy` takes a function that has two arguments: index and item. If `trackBy` is given, Angular tracks changes by the return value of the function.

## Further Reading

* [TSLint - template-use-track-by-function](http://codelyzer.com/rules/template-use-track-by-function/)