Pattern: Missing use of `__dir__`

Issue: -

## Description

This rule checks for places where the `#__dir__` method can replace more
complex constructs to retrieve a canonicalized absolute path to the
current file.

## Examples

```ruby
# bad
path = File.expand_path(File.dirname(__FILE__))

# bad
path = File.dirname(File.realpath(__FILE__))

# good
path = __dir__
```

## Further Reading

* [RuboCop - Style/Dir](https://rubocop.readthedocs.io/en/latest/cops_style/#styledir)
