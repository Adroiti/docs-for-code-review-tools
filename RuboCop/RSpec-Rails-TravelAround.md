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

* [RSpec/Rails/TravelAround](https://docs.rubocop.org/rubocop-rspec_rails/cops_rspecrails.html#rspecrailstravelaround)