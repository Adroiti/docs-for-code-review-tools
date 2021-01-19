Pattern: Use of non-contextual decorator

Issue: -

## Description

Some decorators should only be used in certain class types. For example, the decorator `@Input()` should not be used in a class decorated with `@Injectable()`.

## Further Reading

* [TSLint - contextual-decorator](http://codelyzer.com/rules/contextual-decorator/)