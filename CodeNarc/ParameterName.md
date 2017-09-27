Pattern: Invalid parameter name

Issue: -

## Description

Verifies that the name of each parameter matches a regular expression. This rule applies to method parameters, constructor parameters and closure parameters. By default it checks that parameter names start with a lowercase letter and contains only letters or numbers.

| **Property**         | **Description**                                                                                                                                                                   | **Default Value**        |
| --- | --- | --- |
| regex                | Specifies the regular expression used to validate the parameter name. It is required and cannot be null or empty.                                                                 | /\[a-z\]\[a-zA-Z0-9\]\*/ |
| ignoreParameterNames | Specifies one or more (comma-separated) parameter names that should be ignored (i.e., that should not cause a rule violation). The names may optionally contain wildcards (\*,?). | `null`                   |

## Further Reading

* [CodeNarc - ParameterName](http://codenarc.sourceforge.net/codenarc-rules-naming.html#ParameterName)