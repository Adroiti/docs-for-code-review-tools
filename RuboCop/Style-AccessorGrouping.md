Pattern: Wrong accessor grouping

Issue: -

## Description

Checks for grouping of accessors in class and module bodies. By default it enforces accessors to be placed in grouped declarations, but it can be configured to enforce separating them in multiple declarations.

## Examples

```ruby
# bad
class Foo
  attr_reader :bar
  attr_reader :baz
end

# good
class Foo
  attr_reader :bar, :baz
end
```

## Further Reading

* [RuboCop - Style/AccessorGrouping](https://docs.rubocop.org/rubocop/cops_style.html#styleaccessorgrouping)
