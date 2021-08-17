Pattern: Missing use of new type

Issue: -

## Description

Checks fields on common prefix groups.

## Examples

```ruby
# good
class Types::UserType < Types::BaseObject
  field :registered_at, String, null: false
  field :contact, Types::ContactType, null: false

  def contact
    self
  end
end

class Types::ContactType < Types::BaseObject
  field :phone, String, null: false
  field :first_name, String, null: false
  field :last_name, String, null: false
end

# bad
class Types::UserType < Types::BaseObject
  field :registered_at, String, null: false
  field :contact_phone, String, null: false
  field :contact_first_name, String, null: false
  field :contact_last_name, String, null: false
end
```

## Further Reading

* [RuboCop - GraphQL/ExtractType](https://github.com/DmitryTsepelev/rubocop-graphql/blob/master/lib/rubocop/cop/graphql/extract_type.rb)
