Pattern: Use of `Time.zone=`

Issue: -

## Description

Checks for the use of `Time.zone=` method.

The `zone` attribute persists for the rest of the Ruby runtime, potentially causing
unexpected behavior at a later time.
Using `Time.use_zone` ensures the code passed in the block is the only place Time.zone is affected.
It eliminates the possibility of a `zone` sticking around longer than intended.

## Examples

```ruby
# bad
Time.zone = 'EST'

# good
Time.use_zone('EST') do
end
```

## Further Reading

* [RuboCop - Rails/TimeZoneAssignment](https://docs.rubocop.org/rubocop-rails/cops_rails.html#railstimezoneassignment)
