Pattern: Redundant `within find(​)`

Issue: -

## Description

Checks for redundant `within find(…​)` calls.

## Examples

```ruby
# bad
within find('foo.bar') do
  # ...
end

# good
within 'foo.bar' do
  # ...
end

# bad
within find_by_id('foo') do
  # ...
end

# good
within '#foo' do
  # ...
end
```

## Further Reading

* [Capybara/RedundantWithinFind](https://docs.rubocop.org/rubocop-capybara/cops_capybara.html#capybararedundantwithinfind)