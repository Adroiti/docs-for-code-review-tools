Pattern: Trailing code after class definition

Issue: -

## Description

This rule checks for trailing code after the class definition. Place the first line of class body on its own line.

## Examples

```ruby
# bad
class Foo; def foo; end
end

# good
class Foo
  def foo; end
end
```

## Further Reading

* [RuboCop - Style/TrailingBodyOnClass](https://rubocop.readthedocs.io/en/latest/cops_style/#styletrailingbodyonclass)
