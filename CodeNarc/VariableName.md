Pattern: Invalid variable name

Issue: -

## Description

Verifies that the name of each variable matches a regular expression. By default it checks that non-`final` variable names start with a lowercase letter and contains only letters or numbers. By default, `final` variable names start with an uppercase letter and contain only uppercase letters, numbers and underscores.

| **Property**        | **Description**                                                                                                                                                                  | **Default Value**        |
| --- | --- | --- |
| regex               | Specifies the default regular expression used to validate the variable name. It is required and cannot be null or empty.                                                         | /\[a-z\]\[a-zA-Z0-9\]\*/ |
| finalRegex          | Specifies the regular expression used to validate `final` variable names. It is optional. If not set, then **regex** is used to validate `final` variable names.                 | /\[A-Z\]\[A-Z0-9\_\]\*/  |
| ignoreVariableNames | Specifies one or more (comma-separated) variable names that should be ignored (i.e., that should not cause a rule violation). The names may optionally contain wildcards (\*,?). | `null`                   |

## Further Reading

* [CodeNarc - VariableName](https://codenarc.github.io/CodeNarc/codenarc-rules-naming.html#variablename-rule)