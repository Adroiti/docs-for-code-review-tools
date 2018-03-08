Pattern: Memoized variable not matching method name

Issue: -

## Description

This rule checks for memoized methods whose instance variable name does not match the method name.

## Examples

```ruby
# bad
# Method foo is memoized using an instance variable that is
# not `@foo`. This can cause confusion and bugs.
def foo
  @something ||= calculate_expensive_thing
end

# good
def foo
  @foo ||= calculate_expensive_thing
end

# good
def foo
  @foo ||= begin
    calculate_expensive_thing
  end
end

# good
def foo
  helper_variable = something_we_need_to_calculate_foo
  @foo ||= calculate_expensive_thing(helper_variable)
end
```

## Further Reading

* [RuboCop - Naming/MemoizedInstanceVariableName](https://rubocop.readthedocs.io/en/latest/cops_naming/#namingmemoizedinstancevariablename)
