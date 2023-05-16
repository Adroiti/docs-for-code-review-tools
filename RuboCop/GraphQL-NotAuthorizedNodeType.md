Pattern: Not authorized Node type

Issue: -

## Description

Detects types that implement Node interface and not have `.authorized?` check.
Such types can be fetched by ID and therefore should have type level check to
avoid accidental information exposure.

If `.authorized?` is defined in a parent class, you can add parent to the "SafeBaseClasses"
to avoid offenses in children.

## Examples

```ruby
@example
  # good

  class UserType < BaseType
    implements GraphQL::Types::Relay::Node

    field :uuid, ID, null: false

    def self.authorized?(object, context)
      super && object.owner == context[:viewer]
    end
  end

  # good

  class UserType < BaseType
    implements GraphQL::Types::Relay::Node

    field :uuid, ID, null: false

    class << self
      def authorized?(object, context)
        super && object.owner == context[:viewer]
      end
    end
  end

  # bad

  class UserType < BaseType
    implements GraphQL::Types::Relay::Node

    field :uuid, ID, null: false
  end
```

## Further Reading

* [RuboCop - GraphQL/NotAuthorizedNodeType](https://github.com/DmitryTsepelev/rubocop-graphql/blob/master/lib/rubocop/cop/graphql/not_authorized_node_type.rb)
