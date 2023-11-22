Pattern: Missing class constant visibility

Issue: -

## Description

In PHP 7.1+ it's possible to declare [visibility of class constants](https://wiki.php.net/rfc/class_const_visibility). In a similar vein to optional declaration of visibility for properties and methods which is actually required in sane coding standards, this rule also requires declaring visibility for all class constants.

Rule provides the following settings:

* `fixable`: the rule is not fixable by default because we think it's better to decide about each constant one by one, however you can enable fixability with this option.

```php
const FOO = 1; // visibility missing!
public const BAR = 2; // correct
```

## Further Reading

* [PHP_CodeSniffer - SlevomatCodingStandard.Classes.ClassConstantVisibility](https://github.com/slevomat/coding-standard/blob/master/doc/classes.md#slevomatcodingstandardclassesclassconstantvisibility-)