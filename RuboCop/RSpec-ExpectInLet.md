Pattern: Use of `expect` in `let`

Issue: -

## Description

Do not use `expect` in `let`.

## Examples

```ruby
# bad
let(:foo) do
  expect(something).to eq 'foo'
end

# good
it do
  expect(something).to eq 'foo'
end
```

## Further Reading

* [RSpec - RSpec/ExpectInLet](https://docs.rubocop.org/rubocop-rspec/cops_rspec.html#rspecexpectinlet)