Pattern: Unresolved `TODO` comment

Issue: -

## Description

Developers often add comments to code which is not complete or needs review. Most likely you want to fix or review the code, and then remove the comment, before you consider the code to be production ready.

## Examples

Example of **incorrect** code:

```php
// FIXME: this is not a good idea
// TODO: need code review
do_something_experimental();
```

Example of **correct** code:

```php
// NOT READY FOR PRIME TIME
// but too bad, it is not a predefined warning term
do_something_experimental();
```


## Further Reading

* [PHP_CodeSniffer - Generic.Commenting.Todo](https://github.com/squizlabs/PHP_CodeSniffer/blob/master/src/Standards/Generic/Sniffs/Commenting/TodoSniff.php)