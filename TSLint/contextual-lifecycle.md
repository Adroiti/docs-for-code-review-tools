Pattern: Use of non-contextual lifecycle

Issue: -

## Description

Some life-cycle methods can only be used in certain class types. For example, `ngOnInit()` method should not be used in an `@Injectable` class.

## Further Reading

* [TSLint - contextual-lifecycle](http://codelyzer.com/rules/contextual-lifecycle/)