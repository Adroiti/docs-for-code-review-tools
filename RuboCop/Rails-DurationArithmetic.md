Pattern: Use of duration arithmetic for `Time.current`

Issue: -

## Description

Checks if a duration is added to or subtracted from `Time.current`.

## Examples

```ruby
# bad
Time.current - 1.minute
Time.current + 2.days

# good - using relative would make it harder to express and read
Date.yesterday + 3.days
created_at - 1.minute
3.days - 1.hour

# good
1.minute.ago
2.days.from_now
```

## Further Reading

* [RuboCop - Rails/DurationArithmetic](https://docs.rubocop.org/rubocop-rails/cops_rails.html#railsdurationarithmetic)
