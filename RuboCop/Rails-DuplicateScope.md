Pattern: Duplicate scope for same `where` clause.

Issue: -

## Description

This rule checks for multiple scopes in a model that have the same `where` clause. This
often means you copy/pasted a scope, updated the name, and forgot to change the condition.

## Examples

```ruby
# bad
scope :visible, -> { where(visible: true) }
scope :hidden, -> { where(visible: true) }

# good
scope :visible, -> { where(visible: true) }
scope :hidden, -> { where(visible: false) }
```
## Further Reading

* [Rails - Rails/DuplicateScope](https://docs.rubocop.org/rubocop-rails/cops_rails.html#railsduplicatescope)
