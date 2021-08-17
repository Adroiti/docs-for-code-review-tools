Pattern: Resolver method has too many lines

Issue: -

## Description

Checks if the length of a resolver method exceeds some maximum value. Comment lines can optionally be ignored. The maximum allowed length is configurable using the Max option.

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

* [RuboCop - GraphQL/ResolverMethodLength](https://github.com/DmitryTsepelev/rubocop-graphql/blob/master/lib/rubocop/cop/graphql/resolver_method_length.rb)
