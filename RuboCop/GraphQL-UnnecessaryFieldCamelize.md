Pattern: Unnecessary field camelize

Issue: -

## Description

Checks if each field has an unnecessary camelize.

## Examples

```ruby
# good

class UserType < BaseType
  field :name, String, "Name of the user", null: true
end

# bad

class UserType < BaseType
  field :name, "Name of the user", String, null: true, camelize: true
end
```

## Further Reading

* [RuboCop - GraphQL/UnnecessaryFieldCamelize](https://github.com/DmitryTsepelev/rubocop-graphql/blob/master/lib/rubocop/cop/graphql/unnecessary_field_camelize.rb)
