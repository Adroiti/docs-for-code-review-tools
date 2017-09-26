Pattern: Missing Regex match

Issue: -

## Description

Checks for a specified regular expression that must exist within the source code.

| **Property** | **Description**                                                        | **Default Value** |
| --- | --- | --- |
| regex        | The regular expression to check for. If null or empty then do nothing. | `null`            |

A RuleSet can contain any number of instances of this rule, but each should be configured with a unique rule *name* and *regex*, and (optionally) customized *violationMessage* and *priority*.

## Further Reading

* [CodeNarc - RequiredRegex](http://codenarc.sourceforge.net/codenarc-rules-generic.html#RequiredRegex)