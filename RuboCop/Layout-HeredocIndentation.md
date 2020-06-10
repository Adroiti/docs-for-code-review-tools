Pattern: Malformed heredoc indentation 

Issue: -

## Description

This rule checks the indentation of the here document bodies. The bodies are indented one step.

## Examples

```ruby
# bad
<<-RUBY
something
RUBY

# good
<<~RUBY
  something
RUBY
```

## Further Reading

* [RuboCop - Layout/HeredocIndentation](https://rubocop.readthedocs.io/en/latest/cops_layout/#layoutheredocindentation)
