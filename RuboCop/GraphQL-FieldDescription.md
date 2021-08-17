Pattern: Missing field description

Issue: -

## Description

Checks if each field has a description.

## Examples

```ruby
# good
class UserType < BaseType
  field :name, String, "Name of the user", null: true
end

# bad
class UserType < BaseType
  field :name, String, null: true
end
```

## Further Reading

* [RuboCop - GraphQL/FieldDescription](https://github.com/DmitryTsepelev/rubocop-graphql/blob/master/lib/rubocop/cop/graphql/field_description.rb)
