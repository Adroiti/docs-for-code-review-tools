Pattern: Bisected `attr_accessor`

Issue: -

## Description

Checks for places where `attr_reader` and `attr_writer` for the same method can be combined into single `attr_accessor`.

## Examples

```ruby
# bad
class Foo
  attr_reader :bar
  attr_writer :bar
end

# good
class Foo
  attr_accessor :bar
end
```

## Further Reading

* [RuboCop - Style/BisectedAttrAccessor](https://docs.rubocop.org/rubocop/cops_style.html#stylebisectedattraccessor)
