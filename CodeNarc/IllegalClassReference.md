Pattern: Illegal class reference

Issue: -

## Description

Checks for reference to any of the classes configured in `classNames`.

| **Property** | **Description**                                                                                                                                                                                                                                                                                                                                                               | **Default Value** |
| --- | --- | --- |
| classNames   | Specifies the comma-separated list of (fully-qualified) class names. The class name(s) may optionally include wildcard characters ('\*' or '?'). Note that the '\*' wildcard matches any sequence of zero or more characters in the class/package name, e.g. 'a.\*.SomeClass' matches `a.b.SomeClass` as well as `a.b.c.d.SomeClass`. If `classNames` is null or empty, do nothing. | `null`            |

This rule can be useful for governance and enforcement of *architectural layering*. For instance, making sure that view or model classes, for instance, do not contain references to DAO classes (e.g., \*Dao).

Here is an example configuration of this rule used to ensure that DAO classes are not referenced from within model classes:

``` groovy
ruleset {
    description "Example CodeNarc Ruleset"

    // ...

    IllegalClassReference {
        name = 'DoNotReferenceDaoFromModelClasses'
        priority = 2
        classNames = '*Dao'
        applyToClassNames = 'com.example.model.*'
        description = 'Do not reference DAOs from model classes.'
    }
}
```

A RuleSet can contain any number of instances of this rule, but each should be configured with a unique rule *name* and *classNames*, and (optionally) customized *violationMessage* and *priority*.

## Further Reading

* [CodeNarc - IllegalClassReference](https://codenarc.github.io/CodeNarc/codenarc-rules-generic.html#illegalclassreference-rule)