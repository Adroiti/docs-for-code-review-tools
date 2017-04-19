Pattern: SQL injection

Issue: -

## Description

An SQL injection attack consists of insertion or "injection" of a SQL query
via the input data given to an application. It is a very common attack vector.
This rule looks for strings that resemble SQL statements that are
involved in some form of string building operation. For example:

- "SELECT %s FROM derp;" % var

- "SELECT thing FROM " \+ tab

- "SELECT " \+ val + " FROM " \+ tab + ...

- "SELECT {} FROM derp;".format(var)

Unless care is taken to sanitize and control the input data when building such
SQL statement strings, an injection attack becomes possible. If strings of
this nature are discovered, a LOW confidence issue is reported. In order to
boost result confidence, this rule will also check to see if the
discovered string is in use with standard Python DBAPI calls execute or
executemany. If so, a MEDIUM issue is reported. For example:

- cursor.execute("SELECT %s FROM derp;" % var)

Example of **incorrect** code:

```python

>> Issue: Possible SQL injection vector through string-based query
construction.
   Severity: Medium   Confidence: Low
   Location: ./examples/sql_statements_without_sql_alchemy.py:4
3 query = "DELETE FROM foo WHERE id = '%s'" % identifier
4 query = "UPDATE foo SET value = 'b' WHERE id = '%s'" % identifier
5

```

## Further Reading

  - <https://www.owasp.org/index.php/SQL_Injection>
  - <https://security.openstack.org/guidelines/dg_parameterize-database-queries.html>
* [OpenStack - B608: hardcoded_sql_expressions](https://docs.openstack.org/developer/bandit/plugins/hardcoded_sql_expressions.html)
