Pattern: Use of empty hook

Issue: -

## Description

Checks for empty before and after hooks.

## Examples

```ruby
# bad
before {}
after do; end
before(:all) do
end
after(:all) { }

# good
before { create_users }
after do
  cleanup_users
end
before(:all) do
  create_feed
end
after(:all) { cleanup_feed }
```

## Further Reading

* [RSpec - RSpec/EmptyHook](https://docs.rubocop.org/rubocop-rspec/cops_rspec.html#rspecemptyhook)