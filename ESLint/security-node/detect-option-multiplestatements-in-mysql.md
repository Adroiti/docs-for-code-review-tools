Pattern: Use of `mulitpleStatements:true` for MySQL

Issue: -

## Description

Detects `mulitpleStatements:true` option in `createConnection` method of MySQL. It allows for SQL injection attacks if values are not properly escaped.