Pattern: Rails/DelegateAllowBlank

Issue: -

## Description

This cop looks for delegations that pass :allow_blank as an option
instead of :allow_nil. :allow_blank is not a valid option to pass
to ActiveSupport#delegate.

### Example

```ruby
# bad
delegate :foo, to: :bar, allow_blank: true

# good
delegate :foo, to: :bar, allow_nil: true
```

## Further Reading

* [RuboCop - Rails/DelegateAllowBlank](https://rubocop.readthedocs.io/en/latest/cops_rails/#railsdelegateallowblank)
