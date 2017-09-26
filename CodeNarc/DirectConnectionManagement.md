Pattern: JDBC - direct `Connection` management

Issue: -

## Description

The J2EE standard requires that applications use the container's resource management facilities to obtain connections to resources. Every major web application container provides pooled database connection management as part of its resource management framework. Duplicating this functionality in an application is difficult and error prone, which is part of the reason it is forbidden under the J2EE standard.

Example of violations:

``` groovy
DriverManager.getConnection()
java.sql.DriverManager.getConnection()
```

## Further Reading

* [CodeNarc - DirectConnectionManagement](http://codenarc.sourceforge.net/codenarc-rules-jdbc.html#DirectConnectionManagement)