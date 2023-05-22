Pattern: Missing `max_complexity` configuration

Issue: -

## Description

Detects missing `max_complexity` configuration in schema files.

## Examples

```ruby
@example
  # good

  class AppSchema < BaseSchema
    max_complexity 42
  end
```

## Further Reading

* [RuboCop - GraphQL/MaxComplexitySchema](https://github.com/DmitryTsepelev/rubocop-graphql/blob/master/lib/rubocop/cop/graphql/max_complexity_schema.rb)
