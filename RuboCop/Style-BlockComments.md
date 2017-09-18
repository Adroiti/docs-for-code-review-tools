Pattern: Use of block comment

Issue: -

## Description

This rule looks for uses of block comments (`=begin...=end`). They cannot be preceded by whitespace and are not as easy to spot as regular comments.

## Examples

```ruby
# bad
=begin
comment line
another comment line
=end

# good
# comment line
# another comment line
```

## Further Reading

* [RuboCop - Style/BlockComments](https://rubocop.readthedocs.io/en/latest/cops_style/#styleblockcomments)
* [https://github.com/bbatsov/ruby-style-guide#no-block-comments](https://github.com/bbatsov/ruby-style-guide#no-block-comments)
