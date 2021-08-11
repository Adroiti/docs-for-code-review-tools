Pattern: Excessive whitespace in example description

Issue: -

## Description

Checks for excessive whitespace in example descriptions.

## Examples

```ruby
# bad
it '  has  excessive   spacing  ' do
end

# good
it 'has excessive spacing' do
end


# bad
context '  when a condition   is met  ' do
end

# good
context 'when a condition is met' do
end
```

## Further Reading

* [RSpec - RSpec/ExcessiveDocstringSpacing](https://docs.rubocop.org/rubocop-rspec/cops_rspec.html#rspecexcessivedocstringspacing)
