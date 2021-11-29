Pattern: Duplicate field definition within the same type

Issue: -

## Description

Detects duplicate field definitions within the same type.

## Examples

```ruby
# good
class UserType < BaseType
  field :name, String, null: true
  field :phone, String, null: true do
    argument :something, String, required: false
  end
end

# bad
class UserType < BaseType
  field :name, String, null: true
  field :phone, String, null: true
  field :phone, String, null: true do
    argument :something, String, required: false
  end
end
```

## Further Reading

* [RuboCop - GraphQL/FieldUniqueness](https://github.com/DmitryTsepelev/rubocop-graphql/blob/master/lib/rubocop/cop/graphql/field_uniqueness.rb)
