Pattern: Unnecessary `transient` modifier

Issue: -

## Description

The field is marked as `transient`, but the class isn't Serializable, so marking it as `transient` has no effect. This may be leftover marking from a previous version of the code in which the class was transient, or it may indicate a misunderstanding of how serialization works.

Some Java frameworks change the semantics of the `transient` keyword. For instance, when using Terracotta the `transient` keyword may have slightly different semantics. You may need to turn this rule off depending on which Java frameworks are in use.

Examples:

``` groovy
class MyClass {
    // class not serializable, violation occurs
    transient String property
}

class MySerializableClass implements Serializable {
    // OK, class is serializable
    transient String property
}
```

## Further Reading

* [CodeNarc - UnnecessaryTransientModifier](http://codenarc.sourceforge.net/codenarc-rules-unnecessary.html#UnnecessaryTransientModifier)