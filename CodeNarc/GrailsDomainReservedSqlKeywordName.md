Pattern: Grails - domain reserved `SQL` keyword name

Issue: -

## Description

Forbids usage of SQL reserved keywords as class or field names in Grails domain classes. Naming a domain class (or its field) with such a keyword causes SQL schema creation errors and/or redundant table/column name mappings.

Note: due to limited type information available during CodeNarc's operation, this rule will report fields of type `java.io.Serializable`, but not of its implementations. Please specify any implementations used as domain properties in `additionalHibernateBasicTypes`.

| **Property**                  | **Description**                                                                                                                                                                     | **Default Value** |
| --- | --- | --- |
| additionalHibernateBasicTypes | Comma-separated list of simple class names of additional classes that Hibernate maps as basic types (creates a column for a field of such class). Add your custom basic types here. | `''`              |
| additionalReservedSqlKeywords | Comma-separated list of additional reserved SQL keywords (just in case the 337 keywords of nowadays SQL-\* standards weren't enough).                                               | `''`              |

## Further Reading

* [CodeNarc - GrailsDomainReservedSqlKeywordName](http://codenarc.sourceforge.net/codenarc-rules-grails.html#GrailsDomainReservedSqlKeywordName)