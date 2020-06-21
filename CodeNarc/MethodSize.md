Pattern: Method has too many lines

Issue: -

## Description

Checks if the size of a method exceeds the number of lines specified by the **maxLines** property.

| **Property**      | **Description**                                                                                                                                                                | **Default Value** |
| --- | --- | --- |
| maxLines          | The maximum number of lines allowed in a method definition.                                                                                                                    | 100               |
| ignoreMethodNames | Specifies one or more (comma-separated) method names that should be ignored (i.e., that should not cause a rule violation). The names may optionally contain wildcards (\*,?). | `null`            |

Known Limitations:

-   Annotations on a method are included in the size (line count) for that method.

## Further Reading

* [CodeNarc - MethodSize](https://codenarc.github.io/CodeNarc/codenarc-rules-size.html#methodsize-rule)