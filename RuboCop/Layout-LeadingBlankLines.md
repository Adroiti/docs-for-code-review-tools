Pattern: Unnecessary leading blank line

Issue: -

## Description

This rule checks for unnecessary leading blank lines at the beginning of a file.

## Examples

```ruby
# bad
# (start of file)

class Foo
end

# bad
# (start of file)

# a comment

# good
# (start of file)
class Foo
end

# good
# (start of file)
# a comment
```

## Further Reading

* [RuboCop - Layout/LeadingBlankLines](https://rubocop.readthedocs.io/en/latest/cops_layout/#layoutleadingblanklines)
