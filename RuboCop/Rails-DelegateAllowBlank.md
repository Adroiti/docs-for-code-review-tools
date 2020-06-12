Pattern: Use of `allow_blank` as option to delegate

Issue: -

## Description

This rule looks for delegations that pass `:allow_blank` as an option
instead of `:allow_nil`. `:allow_blank` is not a valid option to pass
to `ActiveSupport#delegate`.

## Examples

```ruby
# bad
delegate :foo, to: :bar, allow_blank: true

# good
delegate :foo, to: :bar, allow_nil: true
```

## Further Reading

* [RuboCop - Rails/DelegateAllowBlank](https://docs.rubocop.org/rubocop-rails/cops_rails.html#railsdelegateallowblank)
