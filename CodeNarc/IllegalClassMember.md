Pattern: Illegal class member

Issue: -

## Description

Checks for classes containing fields/properties/methods matching configured illegal member modifiers or not matching any of the configured allowed member modifiers.

| **Property**                       | **Description**                                                                                                                                                                                                                                                                                                      | **Default Value** |
| --- | --- | --- |
| allowedFieldModifiers              | Specifies one or more groups of whitespace-delimited modifier names (e.g. "public static" or "protected"). Multiple groups are separated by commas (e.g. "private final, protected"). If a field does not match all of the modifiers in any group, then trigger a violation. If `null` or empty, skip this check.    | `null`            |
| allowedMethodModifiers             | Specifies one or more groups of whitespace-delimited modifier names (e.g. "public static" or "protected"). Multiple groups are separated by commas (e.g. "private final, protected"). If a method does not match all of the modifiers in any group, then trigger a violation. If `null` or empty, skip this check.   | `null`            |
| allowedPropertyModifiers           | Specifies one or more groups of whitespace-delimited modifier names (e.g. "public static" or "protected"). Multiple groups are separated by commas (e.g. "private final, protected"). If a property does not match all of the modifiers in any group, then trigger a violation. If `null` or empty, skip this check. | `null`            |
| ignoreMethodNames                  | Specifies one or more (comma-separated) method names that should be ignored (i.e., that should not cause a rule violation). The names may optionally contain wildcards (\*,?).                                                                                                                                       | `null`            |
| ignoreMethodsWith- AnnotationNames | Specifies one or more (comma-separated) annotation names that should be ignored (i.e., methods with those annotations should not cause a rule violation). The names may optionally contain wildcards (\*,?). (Do not include the "@" in the annotation name.                                                         | `null`            |
| illegalFieldModifiers              | Specifies one or more groups of whitespace-delimited modifier names (e.g. "public static" or "protected"). Multiple groups are separated by commas (e.g. "private final, protected"). If a field matches all of the modifiers in any group, then trigger a violation. If `null` or empty, skip this check.           | `null`            |
| illegalMethodModifiers             | Specifies one or more groups of whitespace-delimited modifier names (e.g. "public static" or "protected"). Multiple groups are separated by commas (e.g. "private final, protected"). If a method matches all of the modifiers in any group, then trigger a violation. If `null` or empty, skip this check.          | `null`            |
| illegalPropertyModifiers           | Specifies one or more groups of whitespace-delimited modifier names (e.g. "public static" or "protected"). Multiple groups are separated by commas (e.g. "private final, protected"). If a property matches all of the modifiers in any group, then trigger a violation. If `null` or empty, skip this check.        | `null`            |

Modifiers for fields and methods include:

-   public
-   protected
-   private
-   static
-   final
-   volatile (fields only)
-   transient (fields only)

Modifiers for properties are only:

-   static
-   final

Example of violations for methods:

``` groovy
// IllegalClassMember.allowedMethodModifiers = 'public final, private, protected static'

class SomeClass {
    public method1() { }            // violation
    protected method2() { }         // violation
    protected static method3() { }
}
```

Example of violations for properties:

``` groovy
// IllegalClassMember.illegalPropertyModifiers = 'final'

class SomeClass {
    def property1
    final property2         // violation
    static property3
}
```

A RuleSet can contain any number of instances of this rule, but each should be configured with a unique rule *name* and *classNames*, and (optionally) customized *violationMessage* and *priority*.

## Notes

1.  At least one the `illegalFieldModifiers`, `allowedFieldModifiers`, `illegalPropertyModifiers`, `allowedPropertyModifiers`, `illegalMethodModifiers` or `allowedMethodModifiers` properties must be set (i.e., not null or empty) or else this rule does nothing. In other words, you must configure this rule with at least one kind of illegal or allowed class member.
2.  At least one of the (standard) `applyToClassNames`, `applyToFileNames` or `applyToFilesMatching` properties must be set (i.e., not null or empty) or else this rule does nothing. In other words, you must configure this rule to apply to a specific set of classes or files.

## Further Reading

* [CodeNarc - IllegalClassMember](http://codenarc.sourceforge.net/codenarc-rules-generic.html#IllegalClassMember)