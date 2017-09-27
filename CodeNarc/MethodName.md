Pattern: Invalid method name

Issue: -

## Description

Verifies that the name of each method matches a regular expression. By default it checks that the method name starts with a lowercase letter. Implicit method names are ignored (i.e., 'main' and 'run' methods automatically created for Groovy scripts).

| **Property**      | **Description**                                                                                                                                                                | **Default Value** |
| --- | --- | --- |
| regex             | Specifies the regular expression used to validate the method name. It is required and cannot be null or empty.                                                                 | /\[a-z\] w\*/     |
| ignoreMethodNames | Specifies one or more (comma-separated) method names that should be ignored (i.e., that should not cause a rule violation). The names may optionally contain wildcards (\*,?). | `null`            |

## Further Reading

* [CodeNarc - MethodName](http://codenarc.sourceforge.net/codenarc-rules-naming.html#MethodName)