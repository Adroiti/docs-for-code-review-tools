Pattern: Missing use of `delegate`

Issue: -

## Description

This rule looks for delegations that could have been created
automatically with the `delegate` method.

Safe navigation `&.` is ignored because Rails' `allow_nil`
option checks not just for nil but also delegates if nil
responds to the delegated method.

The `EnforceForPrefixed` option (defaulted to `true`) means that
using the target object as a prefix of the method name
without using the `delegate` method will be a violation.
When set to `false`, this case is legal.

## Examples

```ruby
# bad
def bar
  foo.bar
end

# good
delegate :bar, to: :foo

# good
def bar
  foo&.bar
end

# good
private
def bar
  foo.bar
end

# EnforceForPrefixed: true
# bad
def foo_bar
  foo.bar
end

# good
delegate :bar, to: :foo, prefix: true

# EnforceForPrefixed: false
# good
def foo_bar
  foo.bar
end

# good
delegate :bar, to: :foo, prefix: true
```

## Default configuration

Attribute | Value
--- | ---
EnforceForPrefixed | true

## Further Reading

* [RuboCop - Rails/Delegate](https://docs.rubocop.org/rubocop-rails/cops_rails.html#railsdelegate)
