Pattern: Missing use of new input type

Issue: -

## Description

Checks fields on common prefix groups.

## Examples

```ruby
# good
class UpdateUser < BaseMutation
  argument :uuid, ID, required: true
  argument :user_attributes, UserAttributesInputType
end

# bad
class UpdateUser < BaseMutation
  argument :uuid, ID, required: true
  argument :first_name, String, required: true
  argument :last_name, String, required: true
end
```

## Further Reading

* [RuboCop - GraphQL/ExtractInputType](https://github.com/DmitryTsepelev/rubocop-graphql/blob/master/lib/rubocop/cop/graphql/extract_input_type.rb)
