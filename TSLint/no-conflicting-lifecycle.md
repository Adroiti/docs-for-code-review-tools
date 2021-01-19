Pattern: Use of conflicting lifecycles

Issue: -

## Description

A directive typically should not use both `DoCheck` and `OnChanges` to respond to changes on the same input, as `ngOnChanges` will continue to be called when the default change detector detects changes.

## Further Reading

* [TSLint - no-conflicting-lifecycle](http://codelyzer.com/rules/no-conflicting-lifecycle/)