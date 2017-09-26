Pattern: Private field not `final`

Issue: -

## Description

This rule finds `private` fields that are only set within a *constructor* or *field initializer*. Such fields can safely be made `final`.

| **Property**      | **Description**                                                                                                                                                               | **Default Value** |
| --- | --- | --- |
| ignoreFieldNames  | Specifies one or more (comma-separated) field names that should be ignored (i.e., that should not cause a rule violation). The names may optionally contain wildcards (\*,?). | *null*            |
| ignoreJpaEntities | Specifies whether fields defined inside classes annotated with @Entity or @MappedSuperclass JPA annotations should be ignored (i.e., that should not cause a rule violation). | false             |

## Further Reading

* [CodeNarc - PrivateFieldCouldBeFinal](http://codenarc.sourceforge.net/codenarc-rules-design.html#PrivateFieldCouldBeFinal)