Pattern: Redundant `factory` option

Issue: -

## Description

Checks for redundant `factory` option.

## Examples

```ruby
# bad
association :user, factory: :user

# good
association :user
```

## Further Reading

* [FactoryBot/RedundantFactoryOption](https://docs.rubocop.org/rubocop-factory_bot/cops_factorybot.html#factorybotredundantfactoryoption)
