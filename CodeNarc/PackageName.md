Pattern: Invalid package name

Issue: -

## Description

Verifies that the package name of a class matches a regular expression. By default it checks that the package name consists of only lowercase letters and numbers, separated by periods.

| **Property**        | **Description**                                                                                                 | **Default Value**                       |
| --- | --- | --- |
| regex               | Specifies the regular expression used to validate the package name. It is required and cannot be null or empty. | /\[a-z\]+\[a-z0-9\]\*( .\[a-z0-9\]+)\*/ |
| packageNameRequired | Indicates whether a package name declaration is required for all classes.                                       | `false`                                 |

## Further Reading

* [CodeNarc - PackageName](http://codenarc.sourceforge.net/codenarc-rules-naming.html#PackageName)