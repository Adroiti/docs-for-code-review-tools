Pattern: Redundant `around` hook

Issue: -

## Description

Remove redundant `around` hook.

## Examples

```ruby
# bad
around do |example|
  example.run
end

# good
```

## Further Reading

* [RSpec - RSpec/RedundantAround](https://docs.rubocop.org/rubocop-rspec/cops_rspec.html#rspecredundantaround)
