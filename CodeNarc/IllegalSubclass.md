Pattern: Illegal subclass

Issue: -

## Description

Checks for classes that extend one of the specified set of illegal superclasses.

| **Property**    | **Description**                                                                                                                                                                                                                                                                                                                                                               | **Default Value** |
| --- | --- | --- |
| superclassNames | Specifies the comma-separated list of (fully-qualified) class names. The class name(s) may optionally include wildcard characters ('\*' or '?'). Note that the '\*' wildcard matches any sequence of zero or more characters in the class/package name, e.g. 'a.\*.SomeClass' matches `a.b.SomeClass` as well as `a.b.c.d.SomeClass`. If `classNames` is null or empty, do nothing. | `null`            |

A RuleSet can contain any number of instances of this rule, but each should be configured with a unique rule *name* and *string*, and (optionally) customized *violationMessage* and *priority*.

## Further Reading

* [CodeNarc - IllegalSubclass](https://codenarc.github.io/CodeNarc/codenarc-rules-generic.html#illegalsubclass-rule)