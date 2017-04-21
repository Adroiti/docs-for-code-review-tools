Pattern: Possible SQL injection via string-based query construction

Issue: -

## Description

An SQL injection attack consists of insertion or "injection" of a SQL query
via the input data given to an application. It is a very common attack vector.
This rule looks for strings that resemble SQL statements that are
involved in some form of string building operation. For example:

- `"SELECT %s FROM derp;" % var`
- `"SELECT thing FROM " \+ tab`
- `"SELECT " \+ val + " FROM " \+ tab + ...`
- `"SELECT {} FROM derp;".format(var)`

Unless care is taken to sanitize and control the input data when building such
SQL statement strings, an injection attack becomes possible.


Example of **incorrect** code:

```python
import sqlalchemy

connection = engine.connect()
myvar = 'jsmith' # our intended usage
myvar = 'jsmith or 1=1' # this will return all users
myvar = 'jsmith; DROP TABLE users' # this drops (removes) the users table
query = "select username from users where username = %s" % myvar
result = connection.execute(query)
for row in result:
    print "username:", row['username']
connection.close()
```

Example of **correct** code:

```python
import sqlalchemy

connection = engine.connect()
myvar = 'jsmith' # our intended usage
myvar = 'jsmith or 1=1' # only matches this odd username
query = "select username from users where username = :name"
result = connection.execute(query, name = myvar)
for row in result:
    print "username:", row['username']
connection.close()
```

## Further Reading

* [OWASP - SQL Injection](https://www.owasp.org/index.php/SQL_Injection)
* [OpenStack - Parameterize Database Queries](https://security.openstack.org/guidelines/dg_parameterize-database-queries.html)
* [OpenStack - B608: hardcoded_sql_expressions](https://docs.openstack.org/developer/bandit/plugins/hardcoded_sql_expressions.html)
