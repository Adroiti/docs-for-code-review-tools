Pattern: Use of `map` instead of `pluck`

Issue: -

## Description

This rule enforces the use of `pluck` over `map`.

`pluck` can be used instead of `map` to extract a single key from each element in an enumerable. When called on an Active Record relation, it results in a more efficient query that only selects the necessary key.

## Examples

```ruby
# bad
Post.published.map { |post| post[:title] }
[{ a: :b, c: :d }].collect { |el| el[:a] }

# good
Post.published.pluck(:title)
[{ a: :b, c: :d }].pluck(:a)
```

## Further Reading

* [RuboCop - Rails/Pluck](https://docs.rubocop.org/rubocop-rails/cops_rails.html#railspluck)
