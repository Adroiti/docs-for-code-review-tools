Pattern: Wrong field order

Issue: -

## Description

Fields should be alphabetically sorted within groups.

## Examples

```ruby
# good
class UserType < BaseType
  field :name, String, null: true
  field :phone, String, null: true do
    argument :something, String, required: false
  end
end

# good
class UserType < BaseType
  field :phone, String, null: true

  field :name, String, null: true
end

# bad
class UserType < BaseType
  field :phone, String, null: true
  field :name, String, null: true
end
```

## Further Reading

* [RuboCop - GraphQL/OrderedFields](https://github.com/DmitryTsepelev/rubocop-graphql/blob/master/lib/rubocop/cop/graphql/ordered_fields.rb)
