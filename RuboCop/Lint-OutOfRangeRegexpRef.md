Pattern: Out of range _Regexp_ reference

Issue: -

## Description

This cops looks for references of Regexp captures that are out of range and thus always returns nil.

## Examples

```ruby
/(foo)bar/ =~ 'foobar'

# bad - always returns nil

puts $2 # => nil

# good

puts $1 # => foo
```

## Further Reading

* [RuboCop - Lint/OutOfRangeRegexpRef](https://docs.rubocop.org/rubocop/cops_lint.html#lintoutofrangeregexpref)
