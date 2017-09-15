Pattern: Invalid heredoc delimiter case

Issue: -

## Description

This cop checks that your heredocs are using the configured case.
By default it is configured to enforce uppercase heredocs.

### Example

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

* [RuboCop - Naming/HeredocDelimiterCase](https://rubocop.readthedocs.io/en/latest/cops_naming/#namingheredocdelimitercase)
* [https://github.com/bbatsov/ruby-style-guide#heredoc-delimiters](https://github.com/bbatsov/ruby-style-guide#heredoc-delimiters)
