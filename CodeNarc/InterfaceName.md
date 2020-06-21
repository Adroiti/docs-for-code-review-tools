Pattern: Invalid interface name

Issue: -

## Description

Verifies that the name of an interface matches the regular expression specified in the **regex** property. If that property is null or empty, then this rule is not applied (i.e., it does nothing). It defaults to null, so this rule must be explicitly configured to be active.

| **Property** | **Description**                                                                                                            | **Default Value** |
| --- | --- | --- |
| regex        | Specifies the regular expression used to validate the name of an interface. If null or empty, then this rule does nothing. | `null`            |

## Further Reading

* [CodeNarc - InterfaceName](https://codenarc.github.io/CodeNarc/codenarc-rules-naming.html#interfacename-rule)