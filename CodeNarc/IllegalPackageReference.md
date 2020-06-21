Pattern: Illegal package reference

Issue: -

## Description

Checks for reference to any of the packages configured in `packageNames`.

| **Property** | **Description**                                                                                                                                                                                                                                                                                                                     | **Default Value** |
| --- | --- | --- |
| packageNames | Specifies the comma-separated list of package names. The package name(s) may optionally include wildcard characters ('\*' or '?'). Note that the '\*' wildcard matches any sequence of zero or more characters in the package name, e.g. 'a.\*' matches 'a.b' as well as 'a.b.c.d'. If `packageNames` is null or empty, do nothing. | `null`            |

This rule can be useful for governance and enforcement of *architectural layering*. For instance, making sure that view or model classes, for instance, do not contain references to JDBC-specific packages (e.g. java.sql and javax.sql).

Here is an example configuration of this rule used to ensure that JDBC packages/classes are only referenced within DAO classes:

``` groovy
ruleset {
    description "Example CodeNarc Ruleset"

    // ...

    IllegalPackageReference {
        name = 'UseJdbcOnlyInDaoClasses'
        priority = 2
        packageNames = 'groovy.sql, java.sql, javax.sql'
        doNotApplyToClassNames = 'com.example.framework.dao.*, *Dao, *DaoImpl'
        description = 'Reference to JDBC packages should be restricted to DAO classes.'
    }
}
```

A RuleSet can contain any number of instances of this rule, but each should be configured with a unique rule *name* and *packageNames*, and (optionally) customized *violationMessage* and *priority*.

## Further Reading

* [CodeNarc - IllegalPackageReference](https://codenarc.github.io/CodeNarc/codenarc-rules-generic.html#illegalpackagereference-rule)