Pattern: Unnecessary field alias

Issue: -

## Description

Checks if a field has an unnecessary alias.

## Examples

```ruby
# good

class UserType < BaseType
  field :name, String, "Name of the user", null: true, alias: :real_name
end

# bad

class UserType < BaseType
  field :name, "Name of the user" String, null: true, alias: :name
end
```

## Further Reading

* [RuboCop - GraphQL/UnnecessaryFieldAlias](https://github.com/DmitryTsepelev/rubocop-graphql/blob/master/lib/rubocop/cop/graphql/unnecessary_field_alias.rb)
