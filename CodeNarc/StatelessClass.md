Pattern: Stateless class

Issue: -

## Description

Checks for non-`final` fields on a class. The intent of this rule is to check a configured set of classes that should remain "stateless" and reentrant. One example might be Grails service classes which are singletons, by default, and so they should be reentrant.

This rule ignores `final` fields (either instance or static). Fields that are `static` and non-`final`, however, do cause a violation.

This rule also ignores all classes annotated with the `@Immutable` transformation.  It also ignores all fields annotated with the `@Inject` annotation.

You can configure this rule to ignore certain fields either by name or by type. This can be useful to ignore fields that hold references to (static) dependencies (such as DAOs or Service objects) or static configuration.

| **Property**          | **Description**                                                                                                                                                                                                                                                      | **Default Value** |
| --- | --- | --- |
| ignoreFieldNames      | Specifies one or more (comma-separated) field names that should be ignored (i.e., that should not cause a rule violation). The names may optionally contain wildcards (\*,?).                                                                                        | `null`            |
| addToIgnoreFieldNames | Specifies one or more (comma-separated) field names to be added to the `ignoreFieldNames` property value. This is a special write-only property, and each call to `setAddIgnoreFieldNames()` adds to (rather than overwrites) the list of field names to be ignored. | `null`            |
| ignoreFieldTypes      | Specifies one or more (comma-separated) field types that should be ignored (i.e., that should not cause a rule violation). The names may optionally contain wildcards (\*,?).                                                                                        | `null`            |


## Notes

1.  The `ignoreFieldTypes` property matches the field type name as indicated in the field declaration, only including a full package specification IF it is included in the source code. For example, the field declaration `BigDecimal value` matches an `ignoreFieldTypes` value of `BigDecimal`, but not `java.lang.BigDecimal`.
2.  There is one exception for the `ignoreFieldTypes` property: if the field is declared with a modifier/type of `def`, then the type resolves to `java.lang.Object`.
3.  At least one of the (standard) `applyToClassNames`, `applyToFileNames` or `applyToFilesMatching` properties must be set (i.e., not null or empty) or else this rule does nothing. In other words, you must configure this rule to apply to a specific set of classes or files.
4.  This rule will not catch violations of true *statelessness*/*reentrancy* if you define a `final` field whose value is itself mutable, e.g. a `final HashMap`.

## Further Reading

* [CodeNarc - StatelessClass](https://codenarc.github.io/CodeNarc/codenarc-rules-generic.html#statelessclass-rule)