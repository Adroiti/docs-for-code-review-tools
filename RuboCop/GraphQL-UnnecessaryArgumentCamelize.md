Pattern: Unnecessary argument camelize

Issue: -

## Description

Checks if each argument has an unnecessary camelize.

## Examples

```ruby
# good

class UserType < BaseType
  field :name, String, "Name of the user", null: true do
    argument :filter, String, required: false, camelize: false
  end
end

# good

class UserType < BaseType
  argument :filter, String, required: false, camelize: false
end

# bad

class UserType < BaseType
  argument :filter, String, required: false, camelize: false
end

# bad

class UserType < BaseType
  field :name, String, "Name of the user", null: true do
    argument :filter, String, required: false, camelize: true
  end
end
```

## Further Reading

* [RuboCop - GraphQL/UnnecessaryArgumentCamelize](https://github.com/DmitryTsepelev/rubocop-graphql/blob/master/lib/rubocop/cop/graphql/unnecessary_argument_camelize.rb)
