Pattern: Static `Connection`

Issue: -

## Description

Creates violations when a `java.sql.Connection` object is used as a static field. Database connections stored in static fields will be shared between threads, which is unsafe and can lead to race conditions.

A transactional resource object such as database connection can only be associated with one transaction at a time. For this reason, a connection should not be shared between threads and should not be stored in a static field.

## Further Reading

* [CodeNarc - StaticConnection](https://codenarc.github.io/CodeNarc/codenarc-rules-concurrency.html#staticconnection-rule)