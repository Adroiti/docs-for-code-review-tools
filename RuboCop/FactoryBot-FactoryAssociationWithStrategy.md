Pattern: Hard coding a strategy

Issue: -

## Description

Use definition in factory association instead of hard coding a strategy.

## Examples

```ruby
# bad - only works for one strategy
factory :foo do
  profile { create(:profile) }
end

# good - implicit
factory :foo do
  profile
end

# good - explicit
factory :foo do
  association :profile
end

# good - inline
factory :foo do
  profile { association :profile }
end
```

## Further Reading

* [FactoryAssociationWithStrategy](https://docs.rubocop.org/rubocop-factory_bot/cops_factorybot.html#factorybotfactoryassociationwithstrategy)