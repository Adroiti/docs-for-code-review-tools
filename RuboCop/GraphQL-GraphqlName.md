Pattern: Inconsistent use of `graphql_name`

Issue: -

## Description

Checks consistency of `graphql_name` usage. EnforcedStyle supports two modes:

`only_override` : types and mutations should have graphql_name configured only if it's
 different from the default name

`required` : all types and mutations should have graphql_name configured

## Examples

```ruby
@example EnforcedStyle: only_override (default)
  # good

  class UserType < BaseType
    graphql_name 'Viewer'
  end

  # bad

  class UserType < BaseType
    graphql_name 'User'
  end

@example EnforcedStyle: required
  # good

  class UserType < BaseType
    graphql_name 'User'
  end

  # bad

  class UserType < BaseType
  end
```

## Further Reading

* [RuboCop - GraphQL/GraphqlName](https://github.com/DmitryTsepelev/rubocop-graphql/blob/master/lib/rubocop/cop/graphql/graphql_name.rb)
