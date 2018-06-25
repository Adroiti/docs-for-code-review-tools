Pattern: `AddField` with default value

Issue: -

## Description

Looks for migrations which add new model fields and these fields have a
default value. According to Django docs this may have performance penalties
especially on large tables.

The preferred way is to add a new DB column with `null=True` because it will
be created instantly and then possibly populate the table with the
desired default values.
