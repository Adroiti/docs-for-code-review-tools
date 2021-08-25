Pattern: Missing use of `:hash_key`

Issue: -

## Description

Prevents defining unnecessary resolver methods in cases when `:hash_key` option can be used.

## Examples

```ruby
# good
class Types::UserType < Types::BaseObject
  field :phone, String, null: true, hash_key: :home_phone
end

# bad
class Types::UserType < Types::BaseObject
  field :phone, String, null: true

  def phone
    object[:home_phone]
  end
end
```

## Further Reading

* [RuboCop - GraphQL/FieldHashKey](https://github.com/DmitryTsepelev/rubocop-graphql/blob/master/lib/rubocop/cop/graphql/field_hash_key.rb)
