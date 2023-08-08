Pattern: Invalid heredoc delimiter case

Issue: -

## Description

This rule checks that your heredocs are using the configured case.
By default it is configured to enforce uppercase heredocs.

## Examples

```ruby
# EnforcedStyle: uppercase (default)

# good
<<-SQL
  SELECT * FROM foo
SQL

# bad
<<-sql
  SELECT * FROM foo
sql
```
```ruby
# EnforcedStyle: lowercase

# good
<<-sql
  SELECT * FROM foo
sql

# bad
<<-SQL
  SELECT * FROM foo
SQL
```

## Default configuration

Attribute | Value
--- | ---
EnforcedStyle | uppercase
SupportedStyles | lowercase, uppercase

## Further Reading

* [RuboCop - Naming/HeredocDelimiterCase](https://docs.rubocop.org/rubocop/cops_naming.html#namingheredocdelimitercase)
* [https://github.com/bbatsov/ruby-style-guide#heredoc-delimiters](https://github.com/bbatsov/ruby-style-guide#heredoc-delimiters)
