Pattern: JDBC - `ResultSet` reference

Issue: -

## Description

Checks for direct use of `java.sql.ResultSet`, which is not necessary if using the Groovy **Sql** facility or an ORM framework such as *Hibernate*.

Note: If a violation is triggered from an **import** statement, then you may get multiple violations per import if there are multiple classes in the source file. In that case, the imports are processed once per class.

## Further Reading

* [CodeNarc - JdbcResultSetReference](https://codenarc.github.io/CodeNarc/codenarc-rules-jdbc.html#jdbcresultsetreference-rule)