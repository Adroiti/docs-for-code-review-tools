Pattern: Redundant `travel_back` call

Issue: -

## Description

Checks for redundant `travel_back` calls. Since Rails 5.2, `travel_back` is automatically called at the end of the test.

## Examples

```ruby
# bad
def teardown
  do_something
  travel_back
end

# good
def teardown
  do_something
end

# bad
after do
  do_something
  travel_back
end

# good
after do
  do_something
end
```

## Further Reading

* [RuboCop - Rails/RedundantTravelBack](https://docs.rubocop.org/rubocop-rails/cops_rails.html#railsredundanttravelback)
