Pattern: Use of `DateTime`

Issue: -

## Description

This cop checks for uses of `DateTime` that should be replaced by `Date` or `Time`.

### Example

```ruby
# bad - uses `DateTime` for current time
DateTime.now

# good - uses `Time` for current time
Time.now

# bad - uses `DateTime` for modern date
DateTime.iso8601('2016-06-29')

# good - uses `Date` for modern date
Date.iso8601('2016-06-29')

# good - uses `DateTime` with start argument for historical date
DateTime.iso8601('1751-04-23', Date::ENGLAND)
```

## Further Reading

* [RuboCop - Style/DateTime](https://rubocop.readthedocs.io/en/latest/cops_style/#styledatetime)
* [https://github.com/bbatsov/ruby-style-guide#date--time](https://github.com/bbatsov/ruby-style-guide#date--time)
