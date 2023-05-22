Pattern: Missing `max_depth` configuration

Issue: -

## Description

Detects missing `max_depth` configuration in schema files.

## Examples

```ruby
@example
  # good

  class AppSchema < BaseSchema
    max_depth 42
  end
```

## Further Reading

* [RuboCop - GraphQL/MaxDepthSchema](https://github.com/DmitryTsepelev/rubocop-graphql/blob/master/lib/rubocop/cop/graphql/max_depth_schema.rb)
