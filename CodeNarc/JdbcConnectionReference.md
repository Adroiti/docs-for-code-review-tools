Pattern: JDBC - `Connection` reference

Issue: -

## Description

Checks for direct use of `java.sql.Connection`, which is discouraged and almost never necessary in application code.

Note: If a violation is triggered from an **import** statement, then you may get multiple violations per import if there are multiple classes in the source file. In that case, the imports are processed once per class.

## Further Reading

* [CodeNarc - JdbcConnectionReference](http://codenarc.sourceforge.net/codenarc-rules-jdbc.html#JdbcConnectionReference)