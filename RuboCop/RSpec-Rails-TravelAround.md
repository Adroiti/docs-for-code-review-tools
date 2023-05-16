Pattern: Use of `around`

Issue: -

## Description

Prefer to travel in `before` rather than `around`.

## Examples

```ruby
# bad
around do |example|
  freeze_time do
    example.run
  end
end

# good
before { freeze_time }
```

## Further Reading

* [RSpec - RSpec/Rails/TravelAround](https://docs.rubocop.org/rubocop-rspec/cops_rspec_rails.html#rspecrailstravelaround)