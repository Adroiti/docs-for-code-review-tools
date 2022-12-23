Pattern: Pending example without reason

Issue: -

## Description

Checks for pending or skipped examples without reason.

## Examples

```ruby
# bad
pending 'does something' do
end

# bad
it 'does something', :pending do
end

# bad
it 'does something' do
  pending
end

# bad
xdescribe 'something' do
end

# bad
skip 'does something' do
end

# bad
it 'does something', :skip do
end

# bad
it 'does something' do
  skip
end

# bad
it 'does something'

# good
it 'does something' do
  pending 'reason'
end

# good
it 'does something' do
  skip 'reason'
end

# good
it 'does something', pending: 'reason' do
end

# good
it 'does something', skip: 'reason' do
end
```

## Further Reading

* [RSpec - RSpec/PendingWithoutReason](https://docs.rubocop.org/rubocop-rspec/cops_rspec.html#rspecpendingwithoutreason)
* https://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/PendingWithoutReason