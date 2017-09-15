Pattern: Invalid heredoc delimiter name

Issue: -

## Description

This cop checks that your heredocs are using meaningful delimiters.
By default it disallows `END` and `EO*`, and can be configured through
blacklisting additional delimiters.

### Example

```ruby
# good
<<-SQL
  SELECT * FROM foo
SQL

# bad
<<-END
  SELECT * FROM foo
END

# bad
<<-EOS
  SELECT * FROM foo
EOS
```

## Default configuration

Attribute | Value
--- | ---
Blacklist | END, (?-mix:EO[A-Z]{1})

## Further Reading

* [RuboCop - Naming/HeredocDelimiterNaming](https://rubocop.readthedocs.io/en/latest/cops_naming/#namingheredocdelimiternaming)
* [https://github.com/bbatsov/ruby-style-guide#heredoc-delimiters](https://github.com/bbatsov/ruby-style-guide#heredoc-delimiters)
