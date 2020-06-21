Pattern: Missing text string

Issue: -

## Description

Checks for a specified text string that must exist within the source code.

| **Property** | **Description**                                            | **Default Value** |
| --- | --- | --- |
| string       | The String to check for. If null or empty then do nothing. | `null`            |

A RuleSet can contain any number of instances of this rule, but each should be configured with a unique rule *name* and *string*, and (optionally) customized *violationMessage* and *priority*.

## Further Reading

* [CodeNarc - RequiredString](https://codenarc.github.io/CodeNarc/codenarc-rules-generic.html#requiredstring-rule)