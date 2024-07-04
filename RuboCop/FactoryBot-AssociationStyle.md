Pattern: Inconsistent association style

Issue: -

## Description

Use a consistent style to define associations.

## Examples

#### `EnforcedStyle: implicit (default)`

```ruby
# bad
factory :post do
  association :user
end

# good
factory :post do
  user
end

# bad
factory :post do
  association :user, :author
end

# good
factory :post do
  user factory: %i[user author]
end
```

#### `EnforcedStyle: explicit`

```ruby
# bad
factory :post do
  user
end

# good
factory :post do
  association :user
end

# bad
factory :post do
  user factory: %i[user author]
end

# good
factory :post do
  association :user, :author
end

# good (NonImplicitAssociationMethodNames: ['email'])
sequence :email do |n|
  "person#{n}@example.com"
end

factory :user do
  email
end
```

## Further Reading

* [FactoryBot/AssociationStyle](https://docs.rubocop.org/rubocop-factory_bot/cops_factorybot.html#factorybotassociationstyle)