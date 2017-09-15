Pattern: Extra blank line

Issue: -

## Description

This cops checks for two or more consecutive blank lines.

### Example

```ruby
# bad
some_method




some_method


# good
some_method


some_method
```

## Further Reading

* [RuboCop - Layout/EmptyLines](https://rubocop.readthedocs.io/en/latest/cops_layout/#layoutemptylines)
* [https://github.com/bbatsov/ruby-style-guide#two-or-more-empty-lines](https://github.com/bbatsov/ruby-style-guide#two-or-more-empty-lines)
