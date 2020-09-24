Pattern: Missing use of `super`

Issue: -

## Description

This rule checks for the presence of constructors and life-cycle callbacks without calls to `super`.

## Examples

```ruby
# bad
class Employee < Person
  def initialize(name, salary)
    @salary = salary
  end
end

# good
class Employee < Person
  def initialize(name, salary)
    super(name)
    @salary = salary
  end
end

# bad
class Parent
  def self.inherited(base)
    do_something
  end
end

# good
class Parent
  def self.inherited(base)
    super
    do_something
  end
end
```

## Further Reading

* [RuboCop - Lint/MissingSuper](https://docs.rubocop.org/rubocop/cops_lint.html#lintmissingsuper)
