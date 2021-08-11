Pattern: Missing use of `all` matcher

Issue: -

## Description

Checks that `all` matcher is used instead of iterating over an array.

## Examples

```ruby
# bad
it 'validates users' do
  [user1, user2, user3].each { |user| expect(user).to be_valid }
end

# good
it 'validates users' do
  expect([user1, user2, user3]).to all(be_valid)
end
```

## Further Reading

* [RSpec - RSpec/IteratedExpectation](https://docs.rubocop.org/rubocop-rspec/cops_rspec.html#rspeciteratedexpectation)
* [http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/IteratedExpectation](http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/IteratedExpectation)
