Pattern: Unnecessary spacing

Issue: -

## Description

This rule checks for extra/unnecessary whitespace.

## Examples

```ruby
# good if AllowForAlignment is true
name      = "RuboCop"
# Some comment and an empty line

website  += "/bbatsov/rubocop" unless cond
puts        "rubocop"          if     debug

# bad for any configuration
set_app("RuboCop")
website  = "https://github.com/bbatsov/rubocop"
```

## Default configuration

Attribute | Value
--- | ---
AllowForAlignment | true
ForceEqualSignAlignment | false

## Further Reading

* [RuboCop - Layout/ExtraSpacing](https://rubocop.readthedocs.io/en/latest/cops_layout/#layoutextraspacing)
