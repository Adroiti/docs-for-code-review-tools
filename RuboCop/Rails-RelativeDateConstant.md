Pattern: Relative date assigned to constant

Issue: -

## Description

This rule checks whether constant value isn't relative date. Relative date will be evaluated only once.

## Examples

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

* [RuboCop - Rails/RelativeDateConstant](https://github.com/rubocop-hq/rubocop-rails/tree/master/lib/rubocop/cop/rails#railsrelativedateconstant)
