Pattern: Missing argument description

Issue: -

## Description

Checks if each field has a description.

## Examples

```ruby
# good
class BanUser < BaseMutation
  argument :uuid, ID, required: true, description: "UUID of the user to ban"
end

# bad
class BanUser < BaseMutation
  argument :uuid, ID, required: true
end

```

## Further Reading

* [RuboCop - GraphQL/ArgumentDescription](https://github.com/DmitryTsepelev/rubocop-graphql/blob/master/lib/rubocop/cop/graphql/argument_description.rb)
