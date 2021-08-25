Pattern: Missing use of `:method`

Issue: -

## Description

Prevents defining unnecessary resolver methods in cases when `:method` option can be used.

## Examples

```ruby
# good
class Types::UserType < Types::BaseObject
  field :phone, String, null: true, method: :home_phone
end

# bad
class Types::UserType < Types::BaseObject
  field :phone, String, null: true

  def phone
    object.home_phone
  end
end
```

## Further Reading

* [RuboCop - GraphQL/FieldMethod](https://github.com/DmitryTsepelev/rubocop-graphql/blob/master/lib/rubocop/cop/graphql/field_method.rb)
