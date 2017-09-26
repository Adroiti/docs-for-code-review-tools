Pattern: Use of `instanceof`

Issue: -

## Description

Checks for use of the `instanceof` operator. Prefer using *polymorphism* instead.

Use the `ignoreTypeNames` property to configure ignored type names (the class name specified as the right-hand expression of the `instanceof`). It defaults to ignoring `instanceof` checks against exception classes.

By default, the rule does not analyze test files. This rule sets the default value of the *doNotApplyToFilesMatching* property to ignore file names ending in 'Test.groovy', 'Tests.groovy' or 'TestCase.groovy'.

Example of violations:

``` groovy
class MyClass {
    boolean isRunnable = this instanceof Runnable       // violation
}
```

## Further Reading

* [CodeNarc - Instanceof](http://codenarc.sourceforge.net/codenarc-rules-design.html#Instanceof)