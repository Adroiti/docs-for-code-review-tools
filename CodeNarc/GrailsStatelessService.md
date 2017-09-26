Pattern: Grails - stateless service

Issue: -

## Description

Checks for non-`final` fields on a Grails service class. Grails service classes are singletons by default, and so they should be reentrant. In most cases, this implies (or at least encourages) that they should be stateless.

This rule ignores (i.e., does not cause violations for) the following:

-   All `final` fields (either instance or static). Note that fields that are `static` and non-`final`, however, do cause a violation.
-   Non-`static` properties (i.e., no visibility modifier specified) declared with `def`.
-   All classes annotated with the `@Immutable` transformation.
-   All fields annotated with the `@Inject` annotation.
-   All fields with names matching the *ignoreFieldNames* property.
-   All fields with types matching the *ignoreFieldTypes* property.

The `ignoreFieldNames` property of this rule is pre-configured to ignore the standard Grails service configuration field names ('scope', 'transactional') and the standard injected bean names ('dataSource', 'sessionFactory'), as well as all other field names ending with 'Service'.

| **Property**          | **Description**                                                                                                                                                                                                                                                      | **Default Value**                                           |
| --- | --- | --- |
| ignoreFieldNames      | Specifies one or more (comma-separated) field names that should be ignored (i.e., that should not cause a rule violation). The names may optionally contain wildcards (\*,?).                                                                                        | `'dataSource,scope,sessionFactory, transactional,*Service'` |
| addToIgnoreFieldNames | Specifies one or more (comma-separated) field names to be added to the `ignoreFieldNames` property value. This is a special write-only property, and each call to `setAddIgnoreFieldNames()` adds to (rather than overwrites) the list of field names to be ignored. | `null`                                                      |
| ignoreFieldTypes      | Specifies one or more (comma-separated) field types that should be ignored (i.e., that should not cause a rule violation). The names may optionally contain wildcards (\*,?).                                                                                        | `null`                                                      |

This rule sets the default value of `applyToFilesMatching` to only match files under the 'grails-app/services' folder. You can override this with a different regular expression value if appropriate.

This rule also sets the default value of `applyToClassNames` to only match class names ending in 'Service'. You can override this with a different class name pattern (String with wildcards) if appropriate.

## Notes

1.  The `ignoreFieldTypes` property matches the field type name as indicated in the field declaration, only including a full package specification IF it is included in the source code. For example, the field declaration `BigDecimal value` matches an `ignoreFieldTypes` value of `BigDecimal`, but not `java.lang.BigDecimal`.
2.  There is one exception for the `ignoreFieldTypes` property: if the field is declared with a modifier/type of `def`, then the type resolves to `java.lang.Object`.

## Further Reading

* [CodeNarc - GrailsStatelessService](http://codenarc.sourceforge.net/codenarc-rules-grails.html#GrailsStatelessService)