Pattern: Unused private method

Issue: -

## Description

Checks for private methods that are not referenced within the same class. Note that the `private` modifier is not currently "respected" by Groovy code (i.e., Groovy can access `private` members within other classes).

| **Property**                     | **Description**                                                                                                                                                                                              | **Default Value** |
| --- | --- | --- |
| ignoreMethodsWithAnnotationNames | Specifies one or more (comma-separated) annotation names that mark private methods that should be ignored (i.e., that should not cause a rule violation). The names may optionally contain wildcards (\*,?). | ''                |

Known limitations:

-   Does not recognize method reference through property access (e.g. `getName()` accessed as `x.name`)
-   Does not recognize method invocations when method name is a GString (e.g. `this."$methodName"()`)
-   Does not recognize invoking private method of another instance (i.e. other than `this`)
-   Does not differentiate between multiple private methods with the same name but different parameters (i.e., overloaded)
-   Does not check for unused constructors

## Further Reading

* [CodeNarc - UnusedPrivateMethod](http://codenarc.sourceforge.net/codenarc-rules-unused.html#UnusedPrivateMethod)