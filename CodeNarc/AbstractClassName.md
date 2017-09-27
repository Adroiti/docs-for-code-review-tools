Pattern: Invalid abstract class name

Issue: -

## Description

Verifies that the name of an abstract class matches the regular expression specified in the **regex** property. If that property is null or empty, then this rule is not applied (i.e., it does nothing). It defaults to `null`, so this rule must be explicitly configured to be active. This rule ignores interfaces and is applied only to abstract classes.

| **Property** | **Description**                                                                                                           | **Default Value** |
| --- | --- | --- |
| regex        | Specifies the regular expression used to validate the abstract class name. If null or empty, then this rule does nothing. | `null`            |

## Further Reading

* [CodeNarc - AbstractClassName](http://codenarc.sourceforge.net/codenarc-rules-naming.html#AbstractClassName)