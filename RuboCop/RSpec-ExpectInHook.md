Pattern: Use of `expect` in hook

Issue: -

## Description

Do not use `expect` in hooks such as `before`.

## Examples

```ruby
# bad
before do
  expect(something).to eq 'foo'
end

# bad
after do
  expect_any_instance_of(Something).to receive(:foo)
end

# good
it do
  expect(something).to eq 'foo'
end
```

## Further Reading

* [RSpec - RSpec/ExpectInHook](https://rubocop-rspec.readthedocs.io/en/latest/cops_rspec/#rspecexpectinhook)
* [http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/ExpectInHook](http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/ExpectInHook)
