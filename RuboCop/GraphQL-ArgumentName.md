Pattern: Malformed argument name

Issue: -

## Description

Checks whether field names are snake_case.

## Examples

```ruby
# good
class BanUser < BaseMutation
  argument :user_id, ID, required: true
end

# bad
class BanUser < BaseMutation
  argument :userId, ID, required: true
end
```

## Further Reading

* [RuboCop - GraphQL/ArgumentName](https://github.com/DmitryTsepelev/rubocop-graphql/blob/master/lib/rubocop/cop/graphql/argument_name.rb)
