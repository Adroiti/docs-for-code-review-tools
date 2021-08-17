Pattern: Missing type description

Issue: -

## Description

Checks if a type (object, input, interface, scalar, union, mutation, subscription, and resolver) has a description.

## Examples

```ruby
# good
class Types::UserType < Types::BaseObject
  description "Represents application user"
  # ...
end

# bad
class Types::UserType < Types::BaseObject
  # ...
end
```

## Further Reading

* [RuboCop - GraphQL/ObjectDescription](https://github.com/DmitryTsepelev/rubocop-graphql/blob/master/lib/rubocop/cop/graphql/object_description.rb)
