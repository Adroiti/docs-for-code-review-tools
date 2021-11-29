Pattern: Duplicate argument definition

Issue: -

## Description

Detects duplicate argument definitions.

## Examples

```ruby
# good
class BanUser < BaseMutation
  argument :user_id, ID, required: true
end

# bad
class BanUser < BaseMutation
  argument :user_id, ID, required: true
  argument :user_id, ID, required: true
end
```

## Further Reading

* [RuboCop - GraphQL/ArgumentUniqueness](https://github.com/DmitryTsepelev/rubocop-graphql/blob/master/lib/rubocop/cop/graphql/argument_uniqueness.rb)
