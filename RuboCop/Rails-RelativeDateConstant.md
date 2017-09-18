Pattern: Relative date assigned to constant

Issue: -

## Description

This cop checks whether constant value isn't relative date. Relative date will be evaluated only once.

### Example

```ruby
# bad
class SomeClass
  EXPIRED_AT = 1.week.since
end

# good
class SomeClass
  def self.expired_at
    1.week.since
  end
end
```

## Further Reading

* [RuboCop - Rails/RelativeDateConstant](https://rubocop.readthedocs.io/en/latest/cops_rails/#railsrelativedateconstant)
