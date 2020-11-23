Pattern: Empty class

Issue: -

## Description

Checks for classes and metaclasses without a body. Such empty classes and metaclasses are typically an oversight or we should provide a comment to be clearer what we’re aiming for.

## Examples

```ruby
# bad
class Foo
end

class Bar
  class << self
  end
end

class << obj
end

# good
class Foo
  def do_something
    # ... code
  end
end

class Bar
  class << self
    attr_reader :bar
  end
end

class << obj
  attr_reader :bar
end
```

## Further Reading

* [RuboCop - Lint/EmptyClass](https://docs.rubocop.org/rubocop/cops_lint.html#lintemptyclass)
