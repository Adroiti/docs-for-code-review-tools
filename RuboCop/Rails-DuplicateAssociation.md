Pattern: Duplicate association

Issue: -

## Description

This rule looks for associations that have been defined multiple times in the same file.

When an association is defined multiple times on a model, Active Record overrides the
previously defined association with the new one. Because of this, this cop's autocorrection
simply keeps the last of any duplicates and discards the rest.

## Examples

```ruby
# bad
belongs_to :foo
belongs_to :bar
has_one :foo

# good
belongs_to :bar
has_one :foo
```

## Further Reading

* [Rails - Rails/DuplicateAssociation](https://docs.rubocop.org/rubocop-rails/cops_rails.html#railsduplicateassociation)
