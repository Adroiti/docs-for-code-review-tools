Pattern: Use of `id` column for ordering

Issue: -

## Description

This rule checks for places where ordering by `id` column is used.

Don’t use the `id` column for ordering. The sequence of ids is not guaranteed to be in any particular order, despite often (incidentally) being chronological. Use a timestamp column to order chronologically. As a bonus the intent is clearer.

## Examples

```ruby
# bad
scope :chronological, -> { order(id: :asc) }
scope :chronological, -> { order(primary_key => :asc) }

# good
scope :chronological, -> { order(created_at: :asc) }
```

## Further Reading

* [RuboCop - Rails/OrderById](https://docs.rubocop.org/rubocop-rails/cops_rails.html#railsorderbyid)
