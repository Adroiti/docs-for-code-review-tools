Pattern: Missing grouping of field definitions

Issue: -

## Description

Checks consistency of field definitions. It supports two modes:
- `group_definitions` : all field definitions should be grouped together.
- `define_resolver_after_definition` : if resolver method exists it should
be defined right after the field definition.

## Examples

```ruby
@example EnforcedStyle: group_definitions (default)
  # good
  class UserType < BaseType
    field :first_name, String, null: true
    field :last_name, String, null: true

    def first_name
      object.contact_data.first_name
    end

    def last_name
      object.contact_data.last_name
    end
  end

@example EnforcedStyle: define_resolver_after_definition
  # good
  class UserType < BaseType
    field :first_name, String, null: true

    def first_name
      object.contact_data.first_name
    end

    field :last_name, String, null: true

    def last_name
      object.contact_data.last_name
    end
  end
```

## Further Reading

* [RuboCop - GraphQL/FieldDefinitions](https://github.com/DmitryTsepelev/rubocop-graphql/blob/master/lib/rubocop/cop/graphql/field_definitions.rb)
