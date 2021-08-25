Pattern: Malformed expanded date range

Issue: -

## Description

Checks for expanded date range. Only compatible `..` range is targeted. Incompatible `...` range is ignored.

## Examples

```ruby
# bad
date.beginning_of_day..date.end_of_day
date.beginning_of_week..date.end_of_week
date.beginning_of_month..date.end_of_month
date.beginning_of_quarter..date.end_of_quarter
date.beginning_of_year..date.end_of_year

# good
date.all_day
date.all_week
date.all_month
date.all_quarter
date.all_year
```

## Further Reading

* [RuboCop - Rails/ExpandedDateRange](https://docs.rubocop.org/rubocop-rails/cops_rails.html#railsexpandeddaterange)
