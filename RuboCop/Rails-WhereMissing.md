Pattern: Missing use of `where.missing(...)`

Issue: -

## Description

Use `where.missing(...)` to find missing relationship records.

This rule is enabled in Rails 6.1 or higher.

## Examples

```ruby
# bad
Post.left_joins(:author).where(authors: { id: nil })

# good
Post.where.missing(:author)
```

## Further Reading

* [Rails - Rails/WhereMissing](https://docs.rubocop.org/rubocop-rails/cops_rails.html#railswheremissing)
* https://rails.rubystyle.guide/#finding-missing-relationship-records