Pattern: Unused private field

Issue: -

## Description

Checks for private fields that are not referenced within the same class. Note that the `private` modifier is not currently "respected" by Groovy code (i.e., Groovy can access `private` members within other classes).

By default, fields named `serialVersionUID`, and fields annotated with `groovy.lang.Delegate` are ignored. The rule has a property named *ignoreFieldNames*, which can be set to ignore other field names as well. For instance, to also ignore fields named 'fieldx', set the property to the 'fieldx, serialVersionUID'

| **Property**     | **Description**                                                                                                                                                               | **Default Value** |
| --- | --- | --- |
| ignoreFieldNames | Specifies one or more (comma-separated) field names that should be ignored (i.e., that should not cause a rule violation). The names may optionally contain wildcards (\*,?). | serialVersionUID  |

Known limitations:

-   Does not recognize field access when field name is a GString (e.g. `this."$fieldName"`)
-   Does not recognize access of private field of another instance (i.e. other than `this`)

## Further Reading

* [CodeNarc - UnusedPrivateField](https://codenarc.github.io/CodeNarc/codenarc-rules-unused.html#unusedprivatefield-rule)