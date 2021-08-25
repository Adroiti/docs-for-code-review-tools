Pattern: Use of legacy type-based definition

Issue: -

## Description

Checks whether type definitions are class-based or legacy.
 
## Examples

```ruby
# good
class Example < BaseType
  ....
end

# bad
Example = GraphQL::ObjectType.define do
  ....
  ....
end

```

## Further Reading

* [RuboCop - GraphQL/LegacyDsl](https://github.com/DmitryTsepelev/rubocop-graphql/blob/master/lib/rubocop/cop/graphql/legacy_dsl.rb)
