Pattern: Invalid class name

Issue: -

## Description

Verifies that the name of a class matches a regular expression. By default it checks that the class name starts with an uppercase letter and is followed by zero or more word characters (letters, numbers or underscores) or dollar signs (`$`).

| **Property** | **Description**                                                                                               | **Default Value**    |
| --- | --- | --- |
| regex        | Specifies the regular expression used to validate the class name. It is required and cannot be null or empty. | /(\[A-Z\] w\* $?)\*/ |

## Further Reading

* [CodeNarc - ClassName](http://codenarc.sourceforge.net/codenarc-rules-naming.html#ClassName)