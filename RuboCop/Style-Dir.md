Pattern: Dir

Issue: -

## Description

This cop checks for places where the `#__dir__` method can replace more
complex constructs to retrieve a canonicalized absolute path to the
current file.

### Example

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
