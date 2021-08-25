Pattern: Malformed field name

Issue: -

## Description

Checks whether field names are snake_case.
 
## Examples

```ruby
# good
class UserType < BaseType
  field :first_name, String, null: true
end

# bad
class UserType < BaseType
  field :firstName, String, null: true
end
```

## Further Reading

* [RuboCop - GraphQL/FieldName](https://github.com/DmitryTsepelev/rubocop-graphql/blob/master/lib/rubocop/cop/graphql/field_name.rb)
